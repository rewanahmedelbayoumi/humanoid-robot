# Humanoid Robot — 170 cm Prototype

## Goals
- Final height: **170 cm** from floor to top of head.
- Maintain low mass and a low center of gravity, close to the base.
- Design for on-robot microphone, speaker and local processing; phone app serves as an optional remote control.
- Verify stability and drive-system safety before attempting movement.

> **Status:** Initial requirements; no motor capacity, load rating or autonomous performance has been validated.

## Repository structure
| Folder | Purpose |
|---|---|
| `firmware/` | Microcontroller firmware, sensors and motor control |
| `host/` | Onboard computer services, speech, connectivity and mobile-app API |
| `models/` | CAD, drawings, geometry and other design models |
| `experiments/` | Measurements, test logs and experimental results |
| `docs/` | Requirements, decisions, design notes and safety checklist |

## Day 01 — Requirements and measurements
- [ ] Confirm overall height of 170 cm.
- [ ] Record door widths and the available test area.
- [ ] Prepare front and side orthographic drawings and segment lengths.
- [ ] Fill in estimated part masses and check center-of-mass estimate.
- [ ] Define maximum test load **before motor selection**.
- [ ] Document equipment and budget exclusions.
- [x] Create initial repository layout.

## Initial documents
- [`docs/requirements.md`](docs/requirements.md)
- [`docs/measurements.csv`](docs/measurements.csv)
- [`docs/mass-budget.csv`](docs/mass-budget.csv)
- [`docs/decisions.md`](docs/decisions.md)
- [`docs/safety.md`](docs/safety.md)

## Getting started
1. Fill `docs/measurements.csv` with real measurements.
2. Replace mass placeholders in `docs/mass-budget.csv` with measured or datasheet values.
3. Add drawing files in `models/`.
4. Review the safety checklist before selecting or energizing motors.

## Budget scope
The existing laptop is excluded from the purchase budget. The robot's **onboard hardware**, if required for standalone operation, is **not** implicitly excluded and must be costed separately.

## Team workflow
Create issues for each deliverable. Use branches such as `feature/measurements` and submit pull requests for review. All six members can work in parallel on separate issues.
