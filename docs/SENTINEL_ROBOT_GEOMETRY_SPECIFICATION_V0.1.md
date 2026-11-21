# Sentinel Robot Geometry Specification v0.1
**Status:** Parameter specification for engineering modelling; no dimensions are frozen.

## 1. Purpose
Define the geometric and mass-property inputs required before credible kinematic, stability, inverse-dynamics, actuator and packaging calculations can be completed. This document deliberately defines variables and measurement methods rather than inventing dimensions.

## 2. Coordinate frames
Adopt and document a consistent right-handed coordinate convention:
- **World frame W:** fixed to the surveyed inspection environment.
- **Body frame B:** origin at a declared body reference point; axes aligned to the nominal chassis.
- **Hip/joint frames H_i / J_i:** one per leg and joint, with explicit axis directions and zero-angle definitions.
- **Foot frame F_i:** origin at the nominal foot contact reference.
- **Sensor frames S_i:** calibrated transforms from each sensor to B.

Record transform convention, units, frame owner, calibration method and version. Keep frame names and axis signs consistent across CAD, simulation, firmware and test logs.

## 3. Geometry parameter register
| Parameter | Symbol / record | Required definition | Status |
|---|---|---|---|
| Body length / width / height | L_B, W_B, H_B | External envelope and structural reference surfaces | TBD |
| Body reference origin | O_B | Datum relative to chassis and CoG | TBD |
| Hip locations | r_H,i | 3D position of each of four hip mounts in B | TBD |
| Leg segment lengths | l_i,k | Joint-centre to joint-centre dimensions | TBD |
| Leg segment cross-sections | section_i,k | Shape, wall thickness, material and orientation | TBD |
| Joint axes and zero positions | axis_i,j / q0_i,j | Axis vector, range, hard stops and reference pose | TBD |
| Foot geometry | D_F,i / shape_F,i | Contact patch, sole profile, compliance and replaceable interface | TBD |
| Ground clearance | C_G | Lowest body/part clearance in defined posture | TBD |
| Nominal stance footprint | P_S | Foot contact coordinates and support polygon | TBD |
| Body / payload mounting points | r_P,n | Position, orientation, fastener pattern and load path | TBD |
| Sensor mounting transforms | T_BS,i | Position, orientation, field-of-view and occlusion | TBD |
| Battery / compute locations | r_BAT, r_COMP | Mounting envelope, access, cooling and service clearance | TBD |
| Service / recovery interfaces | r_service | Lift, restraint, manual recovery and handling points | TBD |

No joint count beyond the four legs, joint arrangement, degree of freedom, segment length, foot size or body dimension is selected by this register.

## 4. Mass properties
For every part and assembly, record:
- Unique part/assembly ID and revision.
- Material, manufacturing process and verified origin.
- CAD mass and calculated centre of mass.
- Inertia tensor and reference frame.
- Fasteners, cables, connectors, covers and service hardware included/excluded.
- Source of density/material data and uncertainty.
- Measured mass and balance/CoG measurement once a physical article exists.

Separate the complete robot's baseline mass from mission payload. The preliminary 18–22 kg target applies to the complete robot as defined in the mass-budget framework; do not silently exclude legs, feet, actuators, battery/BMS, compute, baseline sensors, wiring or covers.

## 5. Kinematic and stability inputs
Before calculating workspace or stability, define:
- Joint axes, ranges, velocity and acceleration limits.
- Leg link lengths and collision envelopes.
- Foot contact geometry and allowable contact orientation.
- Stance width/length and nominal body height.
- CoG location for empty, baseline and payload configurations.
- Support polygon and margin calculation method.
- Foot-ground friction evidence and uncertainty.
- Sensor and payload occlusion across the full leg/body workspace.

A static support-polygon check is not a substitute for dynamic stability analysis. Dynamic stability, fall detection and recovery require time-dependent models and separately defined safe test conditions.

## 6. CAD and model-quality requirements
- Use a controlled CAD assembly tree with part numbers and revisions.
- Include real material assignments and realistic fastener/cable allowances.
- Avoid duplicate or hidden geometry that distorts mass properties.
- Define joint mates/constraints and verify degrees of freedom.
- Export a versioned neutral geometry format for simulation where practical.
- Cross-check CAD mass against an independent spreadsheet or script.
- Record model simplifications, omitted components and uncertainty.
- Keep source CAD and generated analysis artifacts traceable.

## 7. Required deliverables before actuator selection
1. Dimensioned chassis and four-leg layout.
2. Joint-axis and range table.
3. Link/foot geometry and collision envelope.
4. Part-level mass, CoG and inertia register.
5. Payload and sensor mounting envelope.
6. Nominal and worst-case CoG configurations.
7. Kinematic reachability and self-collision checks.
8. Static support and preliminary dynamic stability results.
9. Updated mass-budget roll-up with uncertainty.
10. Model review and sign-off record.

## 8. Open decisions
All dimensions, materials, number/type of joints, actuation topology, foot design, payload, sensor layout, battery location, enclosure, cooling path, cable routing and manufacturing process remain open. No supplier, motor, gearbox or battery is selected.

## 9. Evidence boundary
This is a parameter register and modelling specification, not a CAD design, manufactured drawing, prototype record or proof of mobility. Do not use placeholder geometry as a validated product specification. No procurement, fabrication, assembly or field deployment is authorised. Apply PUI89's provenance, repairability, modularity and zero China-origin / China-controlled dependency requirements.
