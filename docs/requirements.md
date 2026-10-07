# Requirements

What the robot has to do. The sizing analysis, the FEA load cases and the acceptance tests all read from this file, so a number here should be one Aidan has set, not a guess. Blank means not decided; the open ones are listed in `TODO.md`.

Last updated: 2026-10-07

## Goals

Stated by Aidan:

- A very finished product that uses what he knows about manufacturing processes, not a prototype.
- Handle a large payload with fast accelerations.
- Keep the end of arm very light, with the motors as far back toward the base as possible.
- Leave room for a vision system and an extra axis later.

## Targets

| Requirement | Target | Notes |
|---|---|---|
| Payload | 10 lb class | Rated at what reach? |
| Reach | | |
| Repeatability | | |
| Maximum joint speed, J1 to J6 | | |
| Maximum joint acceleration, J1 to J6 | | |
| Joint travel, J1 to J6 | | |
| Arm mass | | |
| Mounting | | Floor, table, inverted? |
| Supply voltage | | |
| Air supply at the end of arm | | Pressure, flow, number of lines |
| Electrical connections at the end of arm | | Signals, power |
| Budget | | |

## Constraints

- Motors: NEO 2.0 on J1 and J2, NEO 550 on J3 to J6.
- Motor controllers: SPARK MAX.
- Controller: Teensy.
- Manufacturing processes available: to be listed (3D printing, machining, welding, finishing).
