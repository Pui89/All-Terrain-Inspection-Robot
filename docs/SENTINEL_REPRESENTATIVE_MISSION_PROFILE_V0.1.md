# Sentinel Representative Mission Profile v0.1
**Status:** Proposed engineering baseline — approved as the first representative calculation case, not validated site data.

## 1. Purpose
Define one repeatable, human-supervised mission so that mechanical loads, actuator duty, energy demand and verification requirements can be derived from a consistent use case. This is a design case for engineering calculations, not a claim that a physical Sentinel robot can perform it.

## 2. Mission definition
| Parameter | v0.1 baseline | Status / qualification |
|---|---:|---|
| Mission type | Indoor industrial warehouse / factory inspection | Representative use case |
| Robot | Four-legged quadruped | Product architecture direction |
| Control | Human-supervised; operator retains authority | Requirement |
| Route distance | 300 m total, including return to the start | Proposed planning value |
| Elapsed mission time | 30 min, including preflight and checkpoint dwell | Proposed planning value |
| Walking speed while moving | 0.3–0.5 m/s | Target range, not measured |
| Inspection checkpoints | 5 | Proposed |
| Dwell per checkpoint | 90 s | Planning assumption |
| Supervisor | 1 trained human operator | Proposed |
| Surface | Dry, level or near-level concrete | Assumed site condition |
| Maximum nominal floor slope | 5° | Preliminary boundary; site survey required |
| Floor joints / thresholds | Must be surveyed; height and edge profile TBD | No step-height capability claimed |
| Complete robot mass | 18–22 kg preliminary target | Not a measured mass; see mass-budget framework |
| Mission payload | TBD | Must be included in mass and centre-of-gravity model |

## 3. Time and distance consistency
The 300 m route is the complete planned path, including the return leg. At a constant walking speed:
- 0.3 m/s requires approximately 16.7 min of walking.
- 0.5 m/s requires 10.0 min of walking.

Five 90 s checkpoint stops require 7.5 min. A 3 min preflight allowance leaves approximately 2.8–9.5 min for turns, transitions, brief pauses and route-management overhead, depending on actual walking speed. This is a planning envelope, not a validated duty cycle. If a site survey or later simulation shows the schedule is infeasible, revise the route, dwell time or elapsed time before sizing hardware.

## 4. Mission sequence
1. **Preflight (3 min planning allowance):** operator confirms site authorisation, route, floor condition, exclusion zones, emergency-stop function, battery status, sensor health and communications.
2. **Transit:** robot follows the approved indoor route under human supervision. The planned route length includes the return to the start point.
3. **Checkpoint inspection (5 × 90 s):** stop at each designated point; capture authorised visual/spatial observations; attach timestamp, checkpoint identifier, sensor source and confidence/uncertainty.
4. **Operator review:** present observations and possible anomaly cues for human assessment. The robot does not make safety-critical diagnoses or independently authorise access.
5. **Return and closeout:** reach the designated start/safe point, report faults and energy state, preserve mission records, and allow operator shutdown.

## 5. Operating envelope and exclusions
**Included for this first calculation case:** indoor, dry, concrete floor; supervised movement; modest floor slope up to the provisional 5° boundary; surveyed route; stop-and-observe checkpoints.

**Excluded:** stairs; large steps or unmeasured thresholds; wet, oily, loose or slippery floors; outdoor/all-terrain operation; floodwater; hazardous or explosive atmospheres; chemical exposure; manipulation or load carrying beyond the declared sensor payload; unsupervised autonomy; operation around people without a site-specific risk assessment.

A camera, depth sensor or LiDAR alone cannot establish that an atmosphere is safe. Site safety procedures and appropriately certified instruments are required where relevant.

## 6. Mission acceptance criteria to be defined before testing
- Route completion and return-to-safe-point criteria.
- Maximum permitted path deviation and localisation uncertainty.
- Checkpoint stop-position tolerance and evidence completeness.
- Obstacle response, controlled stop and recovery criteria.
- Communication-loss and low-energy safe-state behaviour.
- Minimum energy reserve at mission end.
- Thermal limits for actuators, drives, battery and onboard compute.
- Operator intervention frequency and allowable mission interruption.

Numerical acceptance thresholds remain TBD until the site, robot geometry, sensor suite and risk assessment are available.

## 7. Inputs required from a real site
Obtain a measured floor plan and route; actual distance; slope profile; joints/threshold heights and edge shapes; floor material/condition; aisle width and turning space; inspection height and viewing angles; obstacle and human-traffic profile; ambient temperature; radio coverage; access restrictions; and emergency procedures. Record source, date, measurement method and uncertainty for every site input.

## 8. Engineering outputs
This mission profile feeds:
- Joint load cases and leg kinematics.
- Geometry and centre-of-gravity requirements.
- Actuator peak, continuous and RMS torque/speed calculations.
- Battery energy, peak current and reserve calculations.
- Thermal duty-cycle analysis.
- Verification gates M1–M7 and mission-level test planning.

## 9. Evidence and change control
All numeric values above are provisional planning assumptions. They are not measured site data, final product specifications, simulation results, or verified performance. Update this document only with traceable site evidence or an approved engineering change. Do not select or purchase hardware, fabricate parts, or conduct field deployment on the basis of this document alone.

**Related:** [Mass Budget & Actuator Sizing Framework v0.1](SENTINEL_MASS_BUDGET_ACTUATOR_SIZING_FRAMEWORK_V0.1.md) · [Joint Load Case Matrix v0.1](SENTINEL_JOINT_LOAD_CASE_MATRIX_V0.1.md) · [Robot Geometry Specification v0.1](SENTINEL_ROBOT_GEOMETRY_SPECIFICATION_V0.1.md)
