# ぽちゃ犬 / Pochaken — Project Proposal

> Stage 2 design proposal / Stage 2企画書。Unless identified as completed, functions and values below are plans, not demonstrated results.

## Vision / 夢

ぽちゃ犬は、いつもそばにいて一緒に過ごしてくれる、手のひらサイズを目指す四足歩行の相棒です。ポケモンや『金色のガッシュ!!』の魔物のように、一緒に経験を重ねる存在を思い描いています。将来は会話や情報案内など、スマートフォンのような機能も目指します。

Pochaken is envisioned as a small four-legged companion that stays close and shares daily experiences. Conversation and helpful information, like a smartphone, are longer-term aspirations.

## Current challenge / 今回の挑戦

RDK X5とUSBカメラで人を検出し、方向を判断して、サーボによる四足歩行につなげる。平坦な屋内で、見守りのもと、短い低速の追従と停止を目指す。手のひらサイズと低予算は目標であり、機体の大きさ、重量、価格は未確定。

A camera detects a person, the RDK X5 estimates their direction, and the controller aims to move a quadruped toward them. Indoor, level-floor operation with close supervision is the initial scenario. Palm size and low cost are goals, not verified specifications.

## User and interaction / 誰のために・どう関わるか

人と一緒に過ごす相棒を求める人を想定する。初期の試験では操作者一人がカメラの前を動き、ぽちゃ犬の方向反応と停止を見守る。人を見失ったとき、画像や指令が途絶えたとき、また停止操作時には止まる設計を目指す。特定人物の識別、会話機能、安全な距離の自動測定は未実装であり今後の検討事項。

## What is new / サンプルからの発展

Stage 1の物体検出サンプルは画面に認識結果を表示した。ぽちゃ犬では、この認識結果を方向判断と足の動き・停止に結びつけ、相棒という目的を持つロボットへ発展させる。四足歩行と追従は未確認。

## What has been completed / できたこと

- RDK X5をセットアップし、Macから接続、Wi-Fiを設定。
- USBカメラと物体検出サンプルを使用し、2本のボトルを検出。
- [Stage 1 result](../usb_camera.png)

Person detection, servo control, four-legged walking and following have not yet been demonstrated.

## Proposed success targets / 試験目標案

These values are preliminary and will be reviewed after initial measurements; none are test results.

| Test | Proposed goal |
|---|---|
| Person direction | In consistent indoor lighting, correctly classify left, center and right in at least 8 of 10 trials. |
| Lost target | Issue a stop command within 1 second of target loss or camera frame interruption; repeat each case five times. |
| BPU detection | Run person detection on RDK X5 for at least 30 seconds while logging performance; record model, resolution, FPS and latency. |
| Walking feasibility | On a level surface, perform a short low-speed walk and stop three consecutive times without a fall, mechanical interference or power reset. |

## Constraints and open questions / 制約と未確認事項

- Four-leg mechanism, number and torque of servos, construction materials, power source, cost and total weight remain open.
- Whether the RDK X5, camera and power supply can be carried by a palm-sized robot needs measurement.
- A single camera does not provide reliable safe distance or obstacle detection on its own. Select and validate a stopping/obstacle strategy before floor-level following.
- Detection of a person is not proof of identifying the same individual.
- Start with a secured one-leg test. Disable motion on stale sensor data or command loss; verify the stop mechanism before movement on the floor.

## Architecture and next steps / 設計と次の一歩

See [system architecture and proposed ROS 2 graph](pochaken-architecture.md). Next: test person detection, prototype one leg, measure load and weight, select a safe power and actuation setup, and then test integration. If walking is not ready, a fixed demonstration can show perception and direction response as an intermediate result; this is a fallback proposal, not a completed demonstration.
