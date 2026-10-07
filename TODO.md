# To do

Everything that needs doing and is not already a planned task in `docs/PLAN.md`. Items are added when they come up and removed when they are done or turned into a task. Where the project stands is in `STATUS.md`; why things are the way they are is in `DECISIONS.md`.

Last updated: 2026-10-07

## Next up

1. Aidan checks the entries in `DECISIONS.md`, corrects anything wrong and confirms or overturns the ones marked Default.
2. Aidan brings the existing work into the repository: gearbox CAD and its Excel driver into `cad/gearboxes/`, the first sizing analysis into `analysis/sizing/`, any arm CAD into `cad/robot/`.
3. Fill in the numbers in `docs/requirements.md`.
4. Fill in `STATUS.md`: where the CAD stands and what exists physically.
5. Answer the blocking decisions below, then plan the first phase in `docs/PLAN.md`.

## Waiting on Aidan: decisions

**Requirements (blocks the sizing analysis)**
- Reach, and the payload it is rated at (10 lb at full reach, or closer in?)
- Target speeds and accelerations per axis, or a target cycle
- Repeatability target
- Joint travel limits
- Mounting (floor, table, inverted?) and supply voltage

**Controller and motor control (blocks electronics and firmware)**
- Which Teensy
- How the Teensy commands the SPARK MAXes. They are built around the FRC control system (roboRIO and REVLib), so this needs confirming before the electronics are designed: CAN, PWM, or something else
- Where each loop closes: position and velocity on the Teensy using the joint encoders, or in the SPARK MAX
- Absolute encoder type and where it sits: on the joint output, on the motor, or both
- Firmware toolchain: PlatformIO, Arduino IDE with Teensyduino, or other
- Control loop rate
- Safety chain: emergency stop, what cuts motor power, brakes or not, behaviour on lost communication

**Mechanical**
- Strain wave reducer: used or not, and on which axes
- Gearbox ratio per axis (comes out of the sizing analysis)
- Belt, shaft or direct drive for the axes whose motors sit back from the joint
- CAD units and drawing standard (mm or inch, ASME Y14.5 or ISO)

**Repository**
- Part numbering for this project. The AWB Addin will assign part numbers once its numbering is decided; what is used until then?
- Licence. The repository is public and has none, which means nobody else may reuse it
- Whether costs belong in the public BOM
- Whether to set up parent and child agents here (`.claude/agents/`, `docs/WORKFLOW.md`, task files) the way the Inventor add-in repository does

## Proposed

- A single robot parameters file (link lengths, masses, ratios, limits) read by both the analysis scripts and the firmware.
- A build log in `docs/log/`, one dated entry per work session, to draw on for the portfolio write-up.
- A setup script for cloud sessions once the firmware toolchain and the Python dependencies are known.

## Follow-ups

None yet.
