# 6-Axis Robot

A 6-axis robot arm designed and built from scratch by Aidan Brown. This repository holds the whole project: CAD, firmware and software, electronics, pneumatics, engineering analysis, BOM and costs, manufacturing details and test records.

**Status:** in design. See [`STATUS.md`](STATUS.md).

## The robot

| | |
|---|---|
| Axes | 6 revolute, J1 (base) to J6 (wrist) |
| Payload class | 10 lb |
| Motors | REV NEO 2.0 on J1 and J2, NEO 550 on J3 to J6 |
| Motor controllers | REV SPARK MAX |
| Reducers | Cycloidal gearboxes of my own design |
| Feedback | Absolute encoder on every axis |
| Controller | Teensy, running control code written from scratch |
| Control | PID with feedforward, friction and gravity compensation |
| End of arm | Pneumatic and electromechanical tooling |
| Planned | Teach pendant, end effectors |
| Possible later | Vision system, extra axis |

The goal is a finished product, not a prototype: a large payload moved with fast accelerations, a very light end of arm, and the motors kept as far back toward the base as possible.

## Layout

| Path | What |
|---|---|
| [`cad/`](cad/) | Inventor parts, assemblies and drawings, vendor models, exported STEP and print files |
| [`firmware/`](firmware/) | Code that runs on the robot: the Teensy controller, later the teach pendant |
| [`software/`](software/) | Code that runs on a PC: tools, simulation, later vision |
| [`electronics/`](electronics/) | KiCad boards, wiring and power diagrams |
| [`pneumatics/`](pneumatics/) | Pneumatic circuit for the end of arm |
| [`analysis/`](analysis/) | Sizing, kinematics, dynamics and controls, FEA, tolerance stacks |
| [`bom/`](bom/) | Bill of materials and costs |
| [`manufacturing/`](manufacturing/) | Released drawings, machining, 3D printing, finishing, assembly |
| [`testing/`](testing/) | Test plans and measured data |
| [`media/`](media/) | Photos, renders and video |
| [`docs/`](docs/) | Requirements, architecture, conventions, plan, references, build log |

## Project files

| File | What |
|---|---|
| [`STATUS.md`](STATUS.md) | Where each big item stands |
| [`TODO.md`](TODO.md) | What is next and what is undecided |
| [`DECISIONS.md`](DECISIONS.md) | Every decision, with who made it |
| [`docs/PLAN.md`](docs/PLAN.md) | Roadmap |
| [`CLAUDE.md`](CLAUDE.md) | Guide for the AI agents that help on this project |

## Cloning

Large files (CAD, STEP, STL, PDF, video) are stored with [Git LFS](https://git-lfs.com). Install it before cloning, or the CAD files will be small text pointers instead of the real files:

```
git lfs install
git clone https://github.com/UWinAidan/6-Axis-Robot.git
```

GitHub Desktop does this for you.
