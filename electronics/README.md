# Electronics

Custom electronics for the robot, designed in KiCad.

| Folder | Holds |
|---|---|
| `boards/` | One KiCad project per board, each in its own folder, with its fabrication outputs and a short `README.md` |
| `wiring/` | System-level diagrams: power distribution, CAN and encoder wiring, the safety chain, connectors and pinouts, the harness through the arm |

Not started. The controller and safety decisions in `TODO.md` come first.

## Rules

- KiCad backup and cache files are gitignored.
- Each board folder says what the board does, its revision, and whether that revision has been built and tested.
- Pinouts are written down once, in `wiring/`, and the firmware follows them.
