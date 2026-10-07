# CAD

Autodesk Inventor models and drawings. Inventor files are binary and stored with Git LFS.

| Folder | Holds |
|---|---|
| `robot/` | The top-level arm assembly and the parts and subassemblies of each axis |
| `gearboxes/` | Cycloidal gearboxes (and the strain wave reducer, if used), with the Excel file that drives the parametric model kept beside it |
| `end-of-arm/` | Tool flange, end effectors, pneumatic and electrical pass-through |
| `purchased/` | Vendor models: motors, controllers, bearings, encoders, fittings. Link to the source in `docs/references/README.md` rather than committing a file we may not redistribute |
| `exports/` | STEP files and print files (STL, 3MF) exported for sharing, simulation or printing, with the revision in the name |

## Rules

- Drawings (`.idw`) live beside the model they detail. Released PDFs go in `manufacturing/drawings/`.
- Do not rename, move or delete files here outside Inventor. Assemblies reference parts by path.
- Keep the Inventor project file (`.ipj`) at the root of `cad/` so every path is relative to it.
- `OldVersions/` and lock files are gitignored. Commit a model when it is in a state worth keeping, with a message that says what changed, because the file itself cannot be diffed.
- An agent in a cloud session cannot open these files. To have a model checked or used in an analysis, export what is needed: a STEP file, a BOM, a parameters table, mass properties.
