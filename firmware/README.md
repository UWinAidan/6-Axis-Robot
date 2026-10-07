# Firmware

Code that runs on the robot.

| Folder | Holds |
|---|---|
| `controller/` | The Teensy robot controller: joint control (PID, feedforward, friction and gravity compensation), SPARK MAX and encoder interfaces, kinematics, motion planning, safety, communication with the PC and the pendant |
| `pendant/` | The teach pendant, when it is built |

Not started. The Teensy model, the toolchain, how the SPARK MAXes are commanded and where the loops close are open; see `TODO.md`. Do not create the project skeleton until those are decided.

## Rules

- Anything that commands motion has limits (position, velocity, current), a defined behaviour on lost communication or a bad encoder reading, and a way to stop.
- Robot parameters (ratios, limits, link lengths) are defined in one place.
- Logic that does not touch hardware (kinematics, trajectory generation, control maths) is written so it can be compiled and tested on a PC.
- Say "not compiled" or "not tested on hardware" for anything that was not.
