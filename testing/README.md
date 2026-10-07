# Testing

| Folder | Holds |
|---|---|
| `plans/` | What is tested, how, and what counts as a pass, tied to `docs/requirements.md` |
| `data/` | Measured data, one folder per test, with a `README.md` giving the date, the setup, the hardware revision and the instruments used |

Covers bench tests of single actuators (backlash, backdrive torque, stiffness, efficiency, temperature) and tests of the whole arm (repeatability, payload, speed).

Not started.

## Rules

- Raw data is never edited. Processing goes in a script beside it.
- A measurement that replaces an estimate in an analysis is noted in that analysis's `README.md`.
