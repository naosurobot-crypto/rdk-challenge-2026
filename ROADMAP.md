# Pochaken / ぽちゃ犬 — Roadmap

Working plan, 24 November 2026. Dates are personal targets and may change. Stage 2 suggested window ends November 26; program final submission is December 15.

## Completed
- [x] RDK X5 setup, Wi-Fi and Mac connection.
- [x] USB camera and sample object detection: two bottles.
- [x] Initial [proposal](docs/pochaken-proposal.md) and [architecture](docs/pochaken-architecture.md).

## Stage 2 — personal submission target November 26
- [ ] Review proposal, numerical targets and architecture with project owner.
- [ ] Publish engineering plan: parts list with quantities and suppliers/SKUs where known; power and interfaces; schedule; five risks, triggers, mitigation and fallbacks; repository structure.
- [ ] Share a public project summary and record its permalink in the participant's Discord thread.
- [ ] Update the project showcase in the official repository and submit or update the relevant PR.

## Stage 3 — proposed milestones
- Nov 27–Dec 1: test person detection; inventory servos; prototype and safely test one secured leg. Record actual results.
- Dec 2–5: investigate gait, load, power and ROS 2 integration. Decide feasibility of a four-legged prototype.
- Dec 6–10: test detection, stopping and feasible motion; record BPU performance. If walking is not feasible, document and demonstrate a fixed prototype as an intermediate fallback. Whether this meets Stage 3 requirements must be checked with organizers.
- Dec 11–14: prepare public demo, code, test evidence and documentation; check official requirements and links.
- Dec 15: final submission target; keep time for corrections.

## Open questions
- Leg design, servo count, torque, power and total weight.
- Whether palm-sized walking can support the RDK X5 and camera.
- Safe distance and obstacle sensing; monocular person detection alone does not reliably measure distance.
- Stopping on target loss, stale camera data and command timeout must be verified before floor tests.
