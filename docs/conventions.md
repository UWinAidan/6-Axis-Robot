# Conventions

Naming, units and file rules for the whole repository. Rules marked (default) were picked at setup and can be changed; see `DECISIONS.md`.

## Axes

- Axes are J1 to J6, base to wrist (default). Use `J1`, not "axis 1", "A1" or "base axis", in file names, code and docs.
- Positive direction and zero position for each joint are defined once, in `analysis/kinematics/`, and everything else follows that.

## Units

- Code and analysis: SI internally (m, kg, s, rad, N, N·m) (default). A name carries the unit when the value is not in an SI base unit: `speedRpm`, `payloadLb`, `angleDeg`.
- CAD units and the drawing standard are open; see `TODO.md`.
- A number in a doc always has its unit.

## File and folder names

- Folders: lowercase, words joined with hyphens (`end-of-arm`, `dynamics-controls`).
- Documents and scripts: lowercase with hyphens or underscores, no spaces.
- CAD files are named by Inventor and the part numbering scheme, which is open. Do not rename CAD files outside Inventor.
- Dates in file names and docs are `YYYY-MM-DD`.

## Part types

The same letters the AWB Addin uses:

| Letter | Meaning |
|---|---|
| P | Purchased |
| M | Manufactured |
| PM | Purchased, modified |
| F | Fastener |
| A | Assembly |
| W | Weldment |
| R | Reference |
| C | Customer supplied |

## Revisions and releases

- Work in progress lives in `cad/`. A drawing or export is released by copying a PDF, STEP or print file into `manufacturing/` or `cad/exports/` with its revision in the name.
- How revisions are lettered or numbered is open until the first release.

## Analyses

Each analysis gets its own folder under `analysis/` with a short `README.md` that says: the question, the inputs and where they came from, how to rerun it, the result, and the date. See `analysis/README.md`.
