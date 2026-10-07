# Analysis

Engineering analysis behind the design.

| Folder | Holds |
|---|---|
| `sizing/` | Gear ratio, torque, speed and acceleration per axis from weights, inertias and motor curves |
| `kinematics/` | Kinematic layout, joint frames and zero positions, forward and inverse kinematics, workspace |
| `dynamics-controls/` | Dynamic model, gravity and friction compensation, control design and tuning |
| `fea/` | Inventor Nastran studies on the loaded parts |
| `tolerance/` | Tolerance stacks on the bearing, gearbox and joint fits |

## One folder per analysis

Each analysis gets its own folder with a `README.md` that says:

1. **Question.** What it is deciding.
2. **Inputs.** Each one with its source: datasheet, CAD export, measurement, or estimate.
3. **How to rerun it.** The script or spreadsheet, and the command if there is one.
4. **Result.** The answer and what was decided from it.
5. **Date**, and the CAD revision or inputs file it was run against.

The sizing analysis is redone whenever the CAD changes the weights and inertias, so it must run from an inputs file, not from numbers typed into the script.

## Rules

- Scripted analyses are in Python. A spreadsheet is fine where it suits the job better.
- No number without a source. Do not invent motor, gearbox or bearing figures.
- For FEA, commit the setup (model, loads, constraints, mesh settings, material) and a report with the result plots. Put raw solver output in a folder named `results/`, which is gitignored.
- An FEA result states its load case and where that load came from, normally the sizing analysis or `docs/requirements.md`.
