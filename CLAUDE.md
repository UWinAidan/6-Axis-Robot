# 6-Axis Robot: agent guide

Aidan is designing and building a 6-axis robot arm from scratch. This repository holds the whole project: CAD, firmware and software, electronics, pneumatics, engineering analysis, BOM and costs, manufacturing details and test records.

- Where each big item stands: `STATUS.md`
- What needs doing next, and what is waiting on Aidan: `TODO.md`
- Decisions made, and who made them: `DECISIONS.md`
- Roadmap and phases: `docs/PLAN.md`
- What the robot has to do (targets and constraints): `docs/requirements.md`
- How the system fits together: `docs/architecture.md`
- Naming, units and file rules: `docs/conventions.md`

## The robot in one paragraph

Six revolute axes, J1 at the base to J6 at the wrist, in the 10 lb payload class. NEO 2.0 brushless motors on J1 and J2 and NEO 550s on J3 to J6, driven by SPARK MAX controllers, with an absolute encoder on every axis. Cycloidal gearboxes of Aidan's own design. A Teensy runs the control code, which is written from scratch. The end of arm is to support pneumatic and electromechanical tooling. A teach pendant is planned; a vision system and an extra axis may follow. `DECISIONS.md` has the detail and says which of this Aidan has confirmed.

## Where things go

| Path | Holds |
|---|---|
| `cad/` | Inventor parts, assemblies and drawings, vendor models, exported STEP and print files |
| `firmware/` | Code that runs on the robot: the Teensy controller, later the teach pendant |
| `software/` | Code that runs on a PC: tools, simulation, later vision |
| `electronics/` | KiCad boards, wiring and power diagrams |
| `pneumatics/` | Pneumatic circuit for the end of arm, valve and fitting selection |
| `analysis/` | Sizing, kinematics, dynamics and controls, FEA, tolerance stacks |
| `bom/` | Bill of materials and costs |
| `manufacturing/` | Released drawings, machining, 3D printing, finishing, assembly instructions |
| `testing/` | Test plans and measured data |
| `media/` | Photos, renders and video |
| `docs/` | Requirements, architecture, conventions, plan, references, build log |

Each folder has a `README.md` that says what belongs in it. Read it before adding files there.

## Know which environment you are in

| | Cloud session (Linux) | Aidan's PC (Windows) |
|---|---|---|
| Markdown, CSV, Python analysis scripts | reads, edits, runs | reads, edits, runs |
| Inventor files (`.ipt`, `.iam`, `.idw`) | **cannot open**: binary, stored in Git LFS | Inventor |
| FEA studies | **cannot run** | Inventor Nastran |
| KiCad projects | text files can be read; nothing can be rendered or checked with ERC or DRC | KiCad |
| Firmware | can be edited; a build only counts if the toolchain is set up and the build was run | builds, flashes |
| Anything on real hardware | impossible | Aidan, by hand |

`CLAUDE_CODE_REMOTE=true` means you are in the cloud.

- Never say something works on the robot unless Aidan tested it on hardware. Write "not tested on hardware" in the task notes and the pull request for anything that was not.
- Never say firmware compiles unless you ran the build and it passed. Say "not compiled" otherwise.
- Do not describe the contents of a CAD file you could not open. Work from exported data (STEP, a BOM export, a drawing PDF, a parameters table) or ask Aidan.

## Engineering rules

- **Numbers need a source.** Every mass, inertia, ratio, torque, speed, stiffness or cost in an analysis or a doc says where it came from: a datasheet (with a link or a file in `docs/references/`), a CAD export, a measurement in `testing/data/`, or "estimate". Do not invent motor, gearbox or bearing figures. If you could not find one, say so and list it under open questions.
- **Units.** Code and analysis use SI (m, kg, s, rad, N, N·m) and carry the unit in the name when it is not SI base (`ratedTorqueNm`, `speedRpm`, `payloadLb`). Convert at the edge. See `docs/conventions.md`.
- **Analyses are rerun, not retyped.** A calculation lives in a script or a spreadsheet with its inputs in one place, so it can be redone when weights and ratios change. A result pasted into a doc names the file and the inputs that produced it.
- **Motion is dangerous.** This arm can move fast with a real payload. Anything that commands motion needs limits (position, velocity, current), a defined behaviour on lost communication or a bad encoder reading, and a way to stop. Do not remove or loosen a limit to make something work; raise it in the task notes.
- **One source of truth.** Robot parameters used by more than one analysis or by the firmware (link lengths, ratios, masses, limits) are defined once and read from there, not copied.

## Files and the public repo

- **This repository is public.** Do not commit vendor quotes, invoices, account numbers, addresses or contact details. `bom/quotes/` and `private/` are gitignored for that.
- Do not commit anything from an employer or a customer: no company names, part numbers, drawings, title blocks or data. This is a personal project.
- Datasheets and vendor CAD models are often not ours to redistribute. Prefer a link in `docs/references/README.md` over a copy.
- Large binary files go through Git LFS; the patterns are in `.gitattributes`. If you add a new binary file type, add its pattern in the same commit.
- Do not commit generated output: Inventor `OldVersions/`, solver results, firmware builds. See `.gitignore`.
- Do not rename, move or delete CAD files. Inventor assemblies reference parts by path, and a moved file breaks them. Ask Aidan to do it in Inventor.

## Tracking files

Three files at the repo root keep the project legible between sessions. Each has one job, so nothing is recorded twice.

| File | Holds | Changes when |
|---|---|---|
| `STATUS.md` | the state of each big item, and what exists physically today | an item changes state |
| `TODO.md` | what is next, what is waiting on Aidan, proposed work, follow-ups | something comes up, gets done, or becomes a planned task |
| `DECISIONS.md` | every decision, with who made it | a decision is made. Append only |

- **Read all three before planning.** Do not plan against a decision without checking `DECISIONS.md`, and do not re-ask a question it already answers.
- **A default is not a decision by Aidan.** When an agent has to pick something to keep work moving, log it in `DECISIONS.md` as "Default" and put the question in `TODO.md`. Aidan can overturn it.
- **When Aidan decides something**, add it to `DECISIONS.md` as "Aidan" and remove the matching line from `TODO.md`.
- When several agents work at once, only the parent session edits these three files, so parallel work never collides on them.

## Working rules

- Do the task you were given and nothing else. Put anything else you notice in `TODO.md` under "Follow-ups".
- Questions only Aidan can answer go in `TODO.md` under "Waiting on Aidan: decisions". Do not invent the answer. Build what is decided and stop at the boundary.
- Keep the docs current in the same change: if a change makes `docs/architecture.md`, `docs/requirements.md` or a folder `README.md` wrong, fix it.
- Write plainly. Short sentences, no filler.
