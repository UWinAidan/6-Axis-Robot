# Decisions

A log of decisions, oldest first. Append only: never edit or delete an entry. To change a decision, add a new entry that says which one it replaces.

Each entry says who decided. **Aidan** means he said so. **Default** means an agent picked it to keep work moving and Aidan has not confirmed it; he can overturn it.

Entries dated 2026-10-07 were recorded when this repository was set up. Several were decided earlier in the project and are logged with that date because the original date was not recorded.

| Date | Decision | By | Where |
|---|---|---|---|
| 2026-10-07 | This repository holds the whole project: CAD, code, agent files, engineering analysis (FEA and others), BOM and costs, manufacturing details | Aidan | `CLAUDE.md` |
| 2026-10-07 | Six axes, built from scratch, in the 10 lb payload class | Aidan | `docs/requirements.md` |
| 2026-10-07 | Design goals: a very finished product; a large payload with fast accelerations; a very light end of arm, with the motors as far back as possible | Aidan | `docs/requirements.md` |
| 2026-10-07 | Motors are brushless (no longer steppers): NEO 2.0 on J1 and J2, NEO 550 on J3 to J6 | Aidan | `docs/architecture.md` |
| 2026-10-07 | Motor controllers are SPARK MAX | Aidan | `docs/architecture.md` |
| 2026-10-07 | The robot controller is a Teensy | Aidan | `docs/architecture.md` |
| 2026-10-07 | An absolute encoder on every axis | Aidan | `docs/architecture.md` |
| 2026-10-07 | Cycloidal gearboxes of Aidan's own design are used. Whether a strain wave reducer is also used is undecided | Aidan | `docs/architecture.md` |
| 2026-10-07 | Control code is written from scratch, not adapted from another robot's code: PID plus feedforward, with friction and gravity compensation | Aidan | `docs/architecture.md` |
| 2026-10-07 | Custom electronics are designed for the robot | Aidan | `electronics/README.md` |
| 2026-10-07 | The end of arm supports pneumatic and electromechanical tooling | Aidan | `docs/architecture.md` |
| 2026-10-07 | A teach pendant and end effectors are planned. A vision system and an extra axis are possible later and the design should not rule them out | Aidan | `docs/PLAN.md` |
| 2026-10-07 | The sizing analysis (gear ratios from expected weights, inertias and motor curves) is redone and iterated before anything is manufactured | Aidan | `analysis/README.md` |
| 2026-10-07 | Agents are guided by `CLAUDE.md` plus three tracking files: `TODO.md`, `STATUS.md`, `DECISIONS.md` | Aidan | `CLAUDE.md` |
| 2026-10-07 | Axes are named J1 (base) to J6 (wrist) | Default | `docs/conventions.md` |
| 2026-10-07 | Code and analysis use SI units internally, with the unit in the name where it is not an SI base unit | Default | `docs/conventions.md` |
| 2026-10-07 | Large binary files (Inventor, STEP, STL, 3MF, PDF, video, photos in `media/`) are stored with Git LFS | Default | `.gitattributes` |
| 2026-10-07 | The folder layout is by discipline (`cad/`, `firmware/`, `electronics/`, ...) rather than by subsystem | Default | `CLAUDE.md` |
| 2026-10-07 | The BOM master is a CSV file (`bom/bom.csv`), using the part type letters from the AWB Addin (P, M, PM, F, A, W, R, C) | Default | `bom/README.md` |
| 2026-10-07 | Vendor quotes and invoices stay out of the public repository (`bom/quotes/` and `private/` are gitignored) | Default | `.gitignore` |
| 2026-10-07 | Scripted analyses are written in Python; spreadsheets are fine where they drive CAD or suit the job better | Default | `analysis/README.md` |
