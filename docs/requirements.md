# Requirements — Day 01

## Fixed
- Total robot height (ground to top of head): **170 cm**.
- Standalone voice interface: microphone, speaker and processing mounted on robot.
- Optional mobile app for monitoring and control; the robot's core interactions should not depend on a separate laptop or a phone.
- Favor low total mass and a low center of gravity.

## Measurements to collect
| Measurement | Value | Units | Owner | Notes |
|---|---|---|---|---|
| Narrowest door clear width | TBD | cm | TBD | Include handles and clearance |
| Test area width | TBD | cm | TBD | Obstacle-free |
| Test area length | TBD | cm | TBD | Obstacle-free |
| Test area ceiling height | TBD | cm | TBD | Robot height = 170 cm |
| Base width / footprint | TBD | cm | TBD | Stability verification needed |
| Head height | TBD | cm | TBD | Orthographic drawing |
| Torso height | TBD | cm | TBD | Orthographic drawing |
| Decorative leg height | TBD | cm | TBD | Orthographic drawing |

## Gates before selecting motors
1. Determine measured/predicted total mass, load distribution and worst-case center of gravity.
2. Determine required motion and speed, load cases and stability margins.
3. Determine maximum safe experimental load and test protocol with appropriate supervision.
4. Select motors/gearboxes only after loads and safety constraints are known.

## Deliverables
- Front and side orthographic sketches in `models/`.
- Measurements and mass estimates in `docs/`.
- Agreed load acceptance criteria (pending review).
