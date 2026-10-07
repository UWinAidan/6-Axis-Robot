# Plan

The roadmap. Phases are **proposed**: Aidan has not confirmed the order. Nothing here is a planned task yet; a phase gets its task list when it is planned.

Last updated: 2026-10-07

| Phase | What | Comes out of it | State |
|---|---|---|---|
| P0 | Requirements and architecture | Filled-in `docs/requirements.md`; the controller and motor control decisions in `TODO.md` answered | Not started |
| P1 | Sizing analysis, redone | Gear ratio, expected torque, speed and acceleration per axis, from weights, inertias and motor curves. Rerunnable from one inputs file | Not started |
| P2 | Actuators | Gearbox design per axis, bench tested for backlash, backdrive torque, stiffness and efficiency | Not started |
| P3 | Arm mechanical design | Full CAD, FEA on the loaded parts, tolerance stacks on the bearing and gearbox fits | Not started |
| P4 | Electronics | Controller board, power distribution, encoder and CAN wiring, safety chain | Not started |
| P5 | Firmware and controls | Joint control on the bench, then kinematics and coordinated motion | Not started |
| P6 | Manufacturing and assembly | Released drawings, BOM with costs, parts made and finished, arm assembled | Not started |
| P7 | Commissioning | Calibration, tuning, measured repeatability and payload against the requirements | Not started |
| P8 | Teach pendant and end effectors | | Not started |
| Later | Vision system, extra axis | | Proposed |

P1 to P3 loop: the sizing analysis is rerun whenever the CAD changes the weights and inertias, until the ratios stop moving.
