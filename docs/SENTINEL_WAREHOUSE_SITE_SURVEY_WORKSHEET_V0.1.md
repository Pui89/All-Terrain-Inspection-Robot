# Sentinel Warehouse Site Survey & Measurement Worksheet v0.1

**Status:** Blank evidence-collection template. No site has been surveyed and no field measurements are asserted by this document.  
**Purpose:** Replace provisional mission assumptions with traceable measurements before geometry, load, actuator, battery or safety calculations are treated as site-specific.

## 1. Survey control record

| Field | Entry |
|---|---|
| Site / facility identifier | TBD |
| Site owner / authorised contact | TBD |
| Survey date and time | TBD |
| Survey team / roles | TBD |
| Permission / work authorisation reference | TBD |
| Drawing / map revision | TBD |
| Measurement equipment and calibration status | TBD |
| Environmental conditions | TBD |
| Survey record revision | TBD |
| Reviewer / approval | TBD |

Do not record personal, security-sensitive or restricted facility information unless authorised and necessary. Store site data with access controls appropriate to the facility.

## 2. Route and mission measurements

Record the route as a sequence of measured segments. Include the outbound and return legs; do not assume the 300 m planning value is correct.

| Segment ID | Start / end landmark | Horizontal distance (m) | Direction / turn | Slope (%) or (°) | Surface condition | Measurement method / source | Uncertainty |
|---|---|---:|---|---:|---|---|---|
| R-01 | TBD | TBD | TBD | TBD | TBD | TBD | TBD |
| R-02 | TBD | TBD | TBD | TBD | TBD | TBD | TBD |
| R-03 | TBD | TBD | TBD | TBD | TBD | TBD | TBD |
| Return | TBD | TBD | TBD | TBD | TBD | TBD | TBD |

**Route totals:** total distance TBD; cumulative ascent/descent TBD; number of turns TBD; narrowest clearance TBD. Record whether the route is one-way, looped or retraced.

## 3. Aisle, clearance and turning envelope

| Measurement | Required value | Method / instrument | Evidence reference | Uncertainty |
|---|---:|---|---|---|
| Narrowest aisle width (m) | TBD | TBD | TBD | TBD |
| Narrowest doorway / access width (m) | TBD | TBD | TBD | TBD |
| Turning-bay length × width (m) | TBD | TBD | TBD | TBD |
| Minimum overhead clearance (m) | TBD | TBD | TBD | TBD |
| Clearance around racks / machinery (m) | TBD | TBD | TBD | TBD |
| Required stand-off distance from hazards (m) | TBD | Site risk assessment | TBD | TBD |

Measure the complete swept envelope needed for the robot, including legs, sensors and any payload—not only the chassis width. Keep a margin for localisation error and operator intervention.

## 4. Floor, joints, thresholds and traction

| Location ID | Floor material / finish | Dry / wet / contaminated | Joint or threshold height (mm) | Edge profile / width | Slope (°) | Traction test or evidence | Photo / drawing ID |
|---|---|---|---:|---|---:|---|---|
| F-01 | TBD | TBD | TBD | TBD | TBD | TBD | TBD |
| F-02 | TBD | TBD | TBD | TBD | TBD | TBD | TBD |
| F-03 | TBD | TBD | TBD | TBD | TBD | TBD | TBD |

Record cracks, drains, grates, loose mats, cables, floor damage and any transition between materials. Do not infer friction coefficient from appearance. Any friction measurement must document method, test surface, test condition and uncertainty. Wet, oily, loose or slippery surfaces remain outside the initial representative mission unless separately assessed and approved.

## 5. Checkpoint measurement sheet

Repeat for each of the five proposed inspection checkpoints, or update the count based on the approved site route.

| Checkpoint | Position / route chainage | Required observation | Camera / sensor viewpoint | Stop footprint available | Dwell time | Human access / exclusion constraints |
|---|---|---|---|---|---:|---|
| CP-01 | TBD | TBD | TBD | TBD | TBD | TBD |
| CP-02 | TBD | TBD | TBD | TBD | TBD | TBD |
| CP-03 | TBD | TBD | TBD | TBD | TBD | TBD |
| CP-04 | TBD | TBD | TBD | TBD | TBD | TBD |
| CP-05 | TBD | TBD | TBD | TBD | TBD | TBD |

Specify viewing height, angle, distance, lighting, occlusion and whether inspection requires the robot to stop, turn or reposition. Do not assume thermal or other anomaly detection without an appropriate sensor, calibration and validation plan.

## 6. Obstacles, people and operational constraints

| Item | Observation / measurement | Location | Frequency / time pattern | Evidence / source | Risk owner / control |
|---|---|---|---|---|---|
| Fixed obstacles / rack legs | TBD | TBD | TBD | TBD | TBD |
| Temporary obstacles / pallets | TBD | TBD | TBD | TBD |
| Pedestrian / vehicle traffic | TBD | TBD | TBD | TBD | TBD |
| Doors / lifts / moving equipment | TBD | TBD | TBD | TBD | TBD |
| Restricted / hazardous zones | TBD | TBD | TBD | TBD | TBD |
| Emergency exits / safe stop areas | TBD | TBD | TBD | TBD | TBD |

Record representative traffic periods, not only a quiet survey window. A human-supervised robot still requires site-specific risk assessment, separation rules, emergency stop access and a defined recovery procedure.

## 7. Environment and connectivity

| Parameter | Measurement / evidence | Instrument / source | Time window | Uncertainty |
|---|---|---|---|---|
| Ambient temperature (°C) | TBD | TBD | TBD | TBD |
| Relative humidity (%) | TBD | TBD | TBD | TBD |
| Lighting / illumination (lux) | TBD | TBD | TBD | TBD |
| Dust / airborne contamination | TBD | TBD | TBD | TBD |
| Radio / Wi-Fi coverage by route segment | TBD | TBD | TBD | TBD |
| Known RF dead zones / interference | TBD | TBD | TBD | TBD |
| Charging / staging location | TBD | TBD | TBD | TBD |

Do not treat network coverage as a safety function unless the architecture and loss-of-link behaviour have been verified. The robot must have a defined safe response to communication loss.

## 8. Mission timing and duty-cycle observation

Use a stopwatch or timestamped log during an authorised representative walk-through. Do not extrapolate from the proposed 30-minute mission without recording actual task times.

| Activity | Planned allowance (min) | Observed time (min) | Evidence / notes |
|---|---:|---:|---|
| Preflight and route authorisation | 3.0 (provisional) | TBD | TBD |
| Transit, all route segments | TBD | TBD | TBD |
| Checkpoint dwell, total | 7.5 (5 × 90 s provisional) | TBD | TBD |
| Turns / repositioning | TBD | TBD | TBD |
| Operator pauses / interventions | TBD | TBD | TBD |
| Return / closeout | Included in route; time TBD | TBD | TBD |
| Total elapsed time | 30 (provisional) | TBD | TBD |

Record walking-only time separately from stop time. Derive actual average transit speed as measured distance divided by walking-only time; do not use total elapsed time for that calculation.

## 9. Data quality and evidence register

For every measurement, retain:
- Unique measurement ID and location reference.
- Value, unit, method, instrument and calibration status.
- Date/time, operator and environmental conditions.
- Raw evidence (approved photo, drawing, instrument export or observation log).
- Uncertainty / tolerance and known limitations.
- Reviewer and acceptance status.

| Evidence ID | Measurement IDs supported | File / drawing reference | Captured by / date | Review status | Limitation |
|---|---|---|---|---|---|
| EV-001 | TBD | TBD | TBD | Pending | TBD |
| EV-002 | TBD | TBD | TBD | Pending | TBD |

## 10. Engineering handoff and decision gates

After survey review, update the following in controlled revisions:
1. Representative Mission Profile: replace provisional route, slope, dwell and timing assumptions only where evidence supports the change.
2. Geometry Specification: use aisle/clearance/turning and checkpoint data to define required envelope, not final dimensions by guesswork.
3. Joint Load Cases: add measured slope, threshold geometry, surface condition and obstacle cases.
4. Actuator sizing: use a time-indexed route and gait profile; do not size from route distance alone.
5. Battery & power: use measured duty cycle and compute/sensor operating modes; include reserve and fault response.
6. Safety case: review pedestrian interaction, emergency stops, communication loss, recovery and restricted zones.

**Gate S0 — Survey completeness:** route and critical surfaces measured; instruments/methods recorded; evidence traceable.  
**Gate S1 — Site suitability:** route, clearance, traffic and hazards reviewed by the authorised site owner.  
**Gate S2 — Engineering update:** mission, geometry, load and energy models revised and independently reviewed.

A failed or incomplete gate means the affected assumptions remain TBD. Do not convert missing measurements into guessed values.

## 11. Important boundary

This worksheet does not authorise a robot trial, site entry, procurement, fabrication or deployment. Any future site visit must be separately authorised by the facility owner and conducted under its safety procedures. The 300 m / 30 min / five-checkpoint / 0.3–0.5 m/s mission remains a provisional planning case until measured evidence is reviewed and formally accepted.
