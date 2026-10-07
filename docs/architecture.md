# Architecture

How the robot fits together. This is the overview; detail lives in the folder for each discipline. Anything not decided is marked **open** and listed in `TODO.md`.

Last updated: 2026-10-07

## Axes

| Axis | Joint | Motor | Reducer | Ratio | Feedback |
|---|---|---|---|---|---|
| J1 | Base rotation | NEO 2.0 | open | open | Absolute encoder |
| J2 | Shoulder | NEO 2.0 | open | open | Absolute encoder |
| J3 | Elbow | NEO 550 | open | open | Absolute encoder |
| J4 | Wrist roll | NEO 550 | open | open | Absolute encoder |
| J5 | Wrist pitch | NEO 550 | open | open | Absolute encoder |
| J6 | Tool roll | NEO 550 | open | open | Absolute encoder |

The joint names in the second column are the usual ones for a 6-axis arm and are placeholders until the kinematic layout is recorded in `analysis/kinematics/`.

Reducers are cycloidal gearboxes of Aidan's own design. Whether a strain wave reducer is used on any axis is open. Motors sit as far back toward the base as possible; how torque reaches the forward joints (belt, shaft, direct) is open.

## Control

```
PC (tools, later vision) ──► Teensy controller ──► SPARK MAX x6 ──► NEO motors ──► reducers ──► joints
        teach pendant ──────►        ▲
                                     └────────── absolute encoders (one per axis)
                                     └────────── end of arm: valves, tooling I/O
```

- The Teensy runs the control code, written from scratch: PID with feedforward, friction and gravity compensation.
- **Open:** which Teensy; how it commands the SPARK MAXes; where the position and velocity loops close; loop rate.
- **Open:** the safety chain (emergency stop, what cuts motor power, brakes, behaviour on lost communication).

## End of arm

Supports pneumatic and electromechanical tooling. The pneumatic circuit is in `pneumatics/`; the electrical interface is in `electronics/`. What is routed through the arm (air lines, signals, power) is open.

## Later

A vision system and an extra axis are possible. The controller I/O, the communication buses and the software structure should leave room for both.
