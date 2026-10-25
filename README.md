# MicroDuck Project

My build of **[Open Duck Mini v2](https://github.com/apirrone/Open_Duck_Mini)**: a 42 cm, 3D-printed bipedal duck robot (inspired by Disney's BDX droid) that walks using a reinforcement-learning policy.

Why this design: it uses **Feetech STS3215** servos, which can be bought in India, and has full editable [Onshape CAD](https://cad.onshape.com/documents/64074dfcfa379b37d8a47762/w/3650ab4221e215a4f65eb7fe/e/0505c262d882183a25049d05) so it can be modified.

## Repository layout

| Path | What's in it |
| --- | --- |
| [`docs/BUILD_PLAN.md`](docs/BUILD_PLAN.md) | Phase-by-phase plan with checklists — start here |
| [`docs/SHOPPING_LIST.md`](docs/SHOPPING_LIST.md) | Parts with India prices and links, plus status tracking |
| [`docs/PRINT_TRACKER.md`](docs/PRINT_TRACKER.md) | Every printed part, copies and progress |
| [`docs/SERVO_MAP.md`](docs/SERVO_MAP.md) | Servo IDs, joint names and calibration record |
| [`docs/BUILD_LOG.md`](docs/BUILD_LOG.md) | Dated notes, problems and fixes |
| `upstream/open_duck_mini` | STL files, print and assembly guides, wiring diagram, pretrained walk policies (submodule, `v2` branch) |
| `upstream/runtime` | Raspberry Pi runtime: motor setup, IMU tests, walking (submodule, `v2` branch) |
| `upstream/playground` | MuJoCo Playground RL training (submodule) |

## Getting the upstream files

```bash
git clone --recurse-submodules https://github.com/yuvarajeshsp-cloud/<this-repo>.git
# or, in an existing clone:
git submodule update --init --depth 1
```

Key files once fetched:

- STL parts: `upstream/open_duck_mini/print/`
- Print guide: `upstream/open_duck_mini/docs/print_guide.md`
- Assembly guide: `upstream/open_duck_mini/docs/assembly_guide.md`
- Wiring diagram: `upstream/open_duck_mini/docs/open_duck_mini_v2_wiring_diagram.png`
- Pretrained walk policy: `upstream/open_duck_mini/BEST_WALK_ONNX_2.onnx`
- Step-by-step guide with photos: [Tnkr build guide](https://tnkr.ai/explore/docs/open-duck-mini/open-duck-mini-v2#home)

## The robot at a glance

| Subsystem | Part |
| --- | --- |
| Brain | Raspberry Pi Zero 2 W (runs the ONNX walking policy) |
| Actuators | 14 × Feetech STS3215 **7.4 V** serial bus servos (10 legs, 4 neck/head) |
| Servo interface | Waveshare Bus Servo Adapter (A), USB to the Pi |
| IMU | BNO055 on the Pi's I2C |
| Power | 2 × 18650 in series (2S, 7.4 V) + 2S BMS + USB-C charger + switch; 5 V UBEC for the Pi |
| Sensors | 2 foot micro-switches per foot |
| Body | ~36 STL files in PLA (15% infill) + TPU sole (40% infill), M3 heat-set inserts |
| Optional "expression" | Eye LEDs, 2 × SG90 antenna servos, speaker (MAX98357A), camera |
| Control | Xbox One controller over Bluetooth |

> ⚠️ Li-ion cells can catch fire if shorted. Check polarity with a multimeter at every step and charge under supervision.
> ⚠️ Configure every servo **on its own** before assembly.

## Credits

Open Duck Mini by Antoine Pirrone (apirrone) and contributors, Apache-2.0. Sponsored by Hugging Face and Pollen Robotics. Actuator models from Rhoban BAM. Join the community: [Discord](https://discord.gg/UtJZsgfQGe).
