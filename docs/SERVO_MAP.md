# Servo map

Configure IDs **one servo at a time** with `python configure_motor.py --id <id>` (from `upstream/runtime/scripts`). Order matters in the runtime.

| ID | Joint | Labelled | Configured | Horn aligned | Offset (rad) | Notes |
| ---: | --- | :---: | :---: | :---: | ---: | --- |
| 10 | right_hip_yaw | [ ] | [ ] | [ ] | | |
| 11 | right_hip_roll | [ ] | [ ] | [ ] | | |
| 12 | right_hip_pitch | [ ] | [ ] | [ ] | | |
| 13 | right_knee | [ ] | [ ] | [ ] | | |
| 14 | right_ankle | [ ] | [ ] | [ ] | | |
| 20 | left_hip_yaw | [ ] | [ ] | [ ] | | |
| 21 | left_hip_roll | [ ] | [ ] | [ ] | | |
| 22 | left_hip_pitch | [ ] | [ ] | [ ] | | |
| 23 | left_knee | [ ] | [ ] | [ ] | | |
| 24 | left_ankle | [ ] | [ ] | [ ] | | |
| 30 | neck_pitch | [ ] | [ ] | [ ] | | |
| 31 | head_pitch | [ ] | [ ] | [ ] | | |
| 32 | head_yaw | [ ] | [ ] | [ ] | | |
| 33 | head_roll | [ ] | [ ] | [ ] | | |

Offsets come from `find_soft_offsets.py` and go into `duck_config.json`.

## Raspberry Pi Zero pin map (from the assembly guide)

| Device | Pin | Pi function |
| --- | ---: | --- |
| BNO055 VIN / GND | 1 / 9 | 3V3 / GND |
| BNO055 SDA / SCL | 3 / 5 | GPIO2 / GPIO3 |
| Left / right foot switch | 15 / 13 | GPIO22 / GPIO27 (GND pin 9) |
| Left / right eye LED (+) | 16 / 18 | GPIO23 / GPIO24 |
| Projector LED (+) | 22 | GPIO25 |
| Antenna PWM left / right | 32 / 33 | GPIO12 / GPIO13 |
| MAX98357A LRC / BCLK / DIN | 35 / 12 / 40 | GPIO19 / GPIO18 / GPIO21 |
