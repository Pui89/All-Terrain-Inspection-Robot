# Sentinel Joint Load Case Matrix v0.1
**Status:** Engineering framework; loads are not yet calculated for final hardware.

## 1. Purpose and assumptions
This matrix translates the approved representative mission into repeatable mechanical load cases for a four-legged quadruped. It does not assume a final degree-of-freedom count, joint arrangement, gait, leg dimensions or actuator type.

The preliminary complete-robot mass target is 18–22 kg. For orientation only, ideal static support shared equally by four feet gives:
\[
F_{foot,static}=\frac{mg}{4}=44.1\text{–}53.9\;N
\]
using standard gravity 9.81 m/s². This is a simplified symmetric-standing reference only. It is not a dynamic peak, actuator rating, impact load, design factor or proof of structural adequacy. Actual load distribution depends on centre of gravity, foot contact, posture, terrain, acceleration and gait.

## 2. Load-case matrix
| ID | Scenario | Required inputs | Primary outputs / checks |
|---|---|---|---|
| JL-01 | Static four-foot stance | Total mass, payload, CoG, foot coordinates, posture | Foot reactions, joint gravity torque, static stability margin |
| JL-02 | Three-foot support / transient unloading | Support-foot set, CoG projection, posture, acceleration | Unequal foot reactions, worst loaded limb, tipping margin |
| JL-03 | Two-foot diagonal support during gait, if selected | Gait sequence, duty factor, phase, body motion | Peak support forces and joint torques |
| JL-04 | Swing-leg lift and placement | Leg mass, segment CoG, angular acceleration, foot trajectory | Swing-joint torque, speed and power |
| JL-05 | Start / stop / longitudinal acceleration | Target acceleration, traction, body and payload mass | Inertial forces, joint torque and slip risk |
| JL-06 | Turning / lateral acceleration | Turn radius or yaw rate, speed, CoG height | Lateral load transfer, joint torque, stability |
| JL-07 | Uphill / downhill at provisional 5° | Slope, friction, posture, speed, braking strategy | Gravity component, traction margin, joint and foot loads |
| JL-08 | Floor joint / threshold crossing | Measured height, edge radius, approach angle, foot size, speed | Contact impulse estimate, peak joint load, foot clearance |
| JL-09 | Unexpected foot slip | Friction estimate, slip velocity, detection latency, recovery action | Recovery torque/speed, stability and safe-stop behaviour |
| JL-10 | Controlled stop / hold on fault | Fault type, body velocity, support state, stop time | Braking/holding torque, safe posture, thermal/electrical limits |
| JL-11 | Payload and CoG extremes | Payload mass, mounting position, tolerance | Worst-case joint torque, support load and stability |
| JL-12 | Impact / stumble / fall arrest | Defined event, impact velocity, compliance, allowable deceleration | Transient loads, structural stress, actuator/back-drive response |
| JL-13 | Repeated mission duty | Time history of each joint torque and speed | RMS torque, thermal accumulation, fatigue duty |
| JL-14 | Low-energy return or stop | Remaining usable energy, route state, terrain and fault condition | Safe stop/return feasibility and reserve requirement |

Not every case is a permitted operating condition. JL-08 through JL-12 are engineering hazard or robustness cases and require carefully controlled simulation or test planning before physical exposure.

## 3. Calculation method
For each body/leg segment, define mass, centre of mass, coordinate frame and inertia tensor. Establish the support polygon and contact state for each instant. Solve whole-body force and moment balance, then use inverse kinematics/dynamics to distribute loads to joints.

For a quasi-static pose:
\[
\sum_i \mathbf{F}_i + m\mathbf{g}=0,\qquad
\sum_i (\mathbf{r}_i\times\mathbf{F}_i)+\mathbf{M}_{ext}=0
\]

For articulated dynamics, use a validated rigid-body model or equivalent formulation. Joint effort can be represented as:
\[
\boldsymbol{\tau}=\mathbf{M}(q)\ddot q+\mathbf{C}(q,\dot q)\dot q+\mathbf{g}(q)+\boldsymbol{\tau}_{friction}-\mathbf{J}(q)^T\mathbf{F}_{contact}
\]
with sign convention defined consistently in the model. This equation is a modelling framework; it does not supply numerical torque without geometry, inertias, motion and contact inputs.

## 4. Required data per case
Record: case ID; mission phase; robot configuration; total and segment masses; payload; CoG; geometry; joint coordinates; foot-contact set; floor friction assumption/evidence; speed and acceleration; external disturbance; model version; solver settings; outputs; uncertainty; safety factor rationale; reviewer; and pass/fail criteria.

## 5. From joint loads to actuator requirements
For each joint and mission time history, calculate:
- Peak positive and negative torque, with duration and recurrence.
- Continuous and RMS torque over the representative mission.
- Joint speed, acceleration and simultaneous torque-speed operating points.
- Mechanical power \(P=\tau\omega\), including regenerative or dissipative behaviour where applicable.
- Transmission efficiency, backlash, compliance, thermal resistance and allowable temperature.
- Holding torque, unpowered behaviour, brake or passive support needs, and fault-state response.

Do not size an actuator using static torque alone. Do not compare motor torque directly with joint output torque without gear ratio, efficiency, thermal limits and duty cycle.

## 6. Required engineering sequence
1. Freeze a versioned geometry and mass-property model for calculation (not a final product freeze).
2. Define candidate gait and support phases; keep alternatives explicit.
3. Build a time-indexed mission motion profile.
4. Run quasi-static checks, then dynamic inverse-dynamics cases.
5. Sweep payload, CoG, friction, slope and uncertainty ranges.
6. Identify worst-case and RMS actuator envelopes.
7. Feed torque/speed/current histories into battery and thermal models.
8. Update mass budget and repeat until the model converges within declared tolerances.

## 7. Open inputs
Final joint count and axes, link lengths, foot geometry, segment masses/inertias, gait, contact friction, payload, CoG, speed/acceleration profiles, threshold geometry, impact assumptions and actuator architecture remain TBD. Use measured or traceable source data; do not invent values to fill gaps.

## 8. Safety and evidence boundary
This matrix is a calculation plan, not evidence of validated walking, balance, fall resistance, obstacle crossing or actuator performance. No procurement, fabrication or field deployment is authorised by this document. Maintain component and supplier provenance and PUI89's zero China-origin / China-controlled dependency policy.
