# Pochaken — Engineering plan / 実施計画

Draft: 24 November 2026. This is a design plan, not proof of implementation. Quantities, suppliers, ratings and dates marked TBD need verification.

## Bill of materials / 部品表

| Item | Quantity and status | Supplier / SKU | Power, interface and questions |
|---|---|---|---|
| RDK X5 | 1, owned | D-Robotics / RDK X5 | Existing dedicated power supply; verify rating, cooling, mass and suitability for carrying onboard. |
| USB webcam | 1, owned | Model and supplier TBD | USB; previously used to detect bottles; resolution and mass TBD. |
| SG90 / MG90S servos | 3 total, owned; model count TBD | Suppliers and exact variants TBD | PWM; check each unit's voltage, current, torque and joint load. Additional number TBD after leg design. |
| PWM output / controller | 1 system planned | TBD; check existing equipment | Confirm interface, signal voltage and compatibility before connecting. |
| Servo power supply | 1 system planned | TBD | Separate appropriately rated supply; sizing depends on number of servos and measured load. Confirm common ground and voltage before wiring. |
| Chassis, legs, joints, fasteners | 1 prototype set planned | Materials and supplier TBD | Mass, strength, attachment and interference TBD. |
| Obstacle / distance sensing | TBD | TBD | Select and validate before autonomous floor following; a person detection box does not reliably measure safe distance. |

Cost: TBD after selection; reuse owned parts and record product links and price before purchase.

## Roadmap / 工程

See [ROADMAP.md](../ROADMAP.md). Stage 2 personal submission target is Nov 26; final program submission is Dec 15. Dates and scope are proposals.

## Top five risks / 主なリスク

| Risk | Trigger | Mitigation | Fallback |
|---|---|---|---|
| Leg cannot carry robot | One-leg load test shows stall, overheating or instability | Measure weight and load; test secured leg, reduce weight, assess alternative joints and servo torque | Fixed rig demonstrating direction response; confirm whether fallback meets Stage 3 rules. |
| Power dips or reset | Voltage falls, servo behaves erratically or board restarts | Select properly sized separate servo supply, measure under load, check wiring | Stop and isolate power; reduce load, retest one servo. |
| Person detection / inference too slow | Measured FPS or response misses preliminary targets | Measure model and resolution on RDK X5; evaluate supported lighter model | Demonstrate stationary detection, record limitations. |
| Target lost or obstacle | Missing/stale detection, stale frame or stop failure | Timeout and stop commands; supervised tests; select obstacle sensing before floor following | Disable motion; use a secured rig until verified. |
| Schedule / component delay | Parts or test milestones delayed | Reuse owned hardware; prioritize detection and safe one-leg test | Document results and unresolved work; contact organizers about eligibility. |

## Planned repository structure / リポジトリ構成案

- `README.md`: project overview and links.
- `ROADMAP.md`: milestones and progress.
- `docs/`: proposal, architecture, engineering plan, future test results.
- `src/`, `launch/`, `config/`, `models/`, `tests/`: future source, ROS 2 launch/config, model instructions and tests. These directories are planned, not yet implemented.

## Review / 確認

Part specifications, source, quantities, schedule and numerical goals need review by the project owner. No person-following, gait or safety test is claimed as complete.
