# BOM and costs

`bom.csv` is the master bill of materials: every part in the robot, purchased or made.

| Column | Meaning |
|---|---|
| `item` | Line number |
| `part_number` | Part number (numbering scheme is open; see `TODO.md`) |
| `name` | Part name |
| `type` | P, M, PM, F, A, W, R or C; see `docs/conventions.md` |
| `subsystem` | Base, J1 to J6, end of arm, electronics, pneumatics |
| `qty` | Quantity per robot |
| `material` | For manufactured parts |
| `finish` | Process applied: anodise, plating, heat treatment |
| `process` | How it is made: machined, 3D printed, welded, laser cut |
| `supplier` | For purchased parts |
| `supplier_pn` | Supplier part number |
| `unit_cost_cad` | Cost each, Canadian dollars |
| `ext_cost_cad` | `qty` times `unit_cost_cad` |
| `status` | To design, designed, ordered, received, made |
| `notes` | |

## Rules

- This repository is public. Vendor quotes, invoices and anything with account or contact details go in `bom/quotes/`, which is gitignored and stays on Aidan's PC.
- A cost says where it came from in `notes`: a quote, a web price with the date, or an estimate.
- Inventor can export an assembly BOM; that export is an input to this file, not a replacement for it.
