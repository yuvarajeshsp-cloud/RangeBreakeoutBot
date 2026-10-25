# Build plan

Work through the phases in order. Tick boxes as you go and add notes to [BUILD_LOG.md](BUILD_LOG.md).

## Phase 0 — Read before you buy
- [ ] Read `upstream/open_duck_mini/README.md`, `docs/print_guide.md` and `docs/assembly_guide.md`
- [ ] Read the [Tnkr guide](https://tnkr.ai/explore/docs/open-duck-mini/open-duck-mini-v2#home). It's the most complete build guide
- [ ] Study the wiring diagram: `upstream/open_duck_mini/docs/open_duck_mini_v2_wiring_diagram.png`
- [ ] Open the [Onshape CAD](https://cad.onshape.com/documents/64074dfcfa379b37d8a47762/w/3650ab4221e215a4f65eb7fe/e/0505c262d882183a25049d05) and look at how the parts fit
- [ ] Check the [official BOM sheet](https://docs.google.com/spreadsheets/d/1gq4iWWHEJVgAA_eemkTEsshXqrYlFxXAPwO515KpCJc/edit?usp=sharing) for screw counts and bearing quantities
- [ ] Join the [Discord](https://discord.gg/UtJZsgfQGe)

## Phase 1 — Order parts
- [ ] Order everything in [SHOPPING_LIST.md](SHOPPING_LIST.md). Servos first, they're the long pole
- [ ] Confirm the servos are the **7.4 V STS3215 (C001, 1:345 gear)**. The pretrained policy is tuned for this exact version

## Phase 2 — Print (while parts ship)
- [ ] Print a test piece and check an STS3215 fits snugly, a 608 bearing presses in, and an M3 insert sets cleanly
- [ ] PLA at 15% infill; `foot_bottom_tpu.stl` in TPU at 40% infill
- [ ] Print everything in [PRINT_TRACKER.md](PRINT_TRACKER.md)
- [ ] Record printer, filament and slicer settings in the build log

## Phase 3 — Battery pack and power (bench)
- [ ] Charge both 18650 cells to the same voltage (within 0.05 V) before putting them in the holder
- [ ] Build the 2S pack: holder → BMS (B+, B−, BM midpoint) → switch → XT30 out; USB-C charger board to the BMS P+/P−
- [ ] Wire the UBEC (7.4 V in, 5 V out for the Pi)
- [ ] Check every output with a multimeter **before** connecting anything: ~7.4–8.4 V raw, 5.0 V from the UBEC

## Phase 4 — Raspberry Pi setup
- [ ] Flash Raspberry Pi OS Lite 64-bit (or the pre-built Duck image linked in `upstream/runtime/README.md`), enable SSH
- [ ] Solder the GPIO header; inspect for solder bridges
- [ ] Follow `upstream/runtime/README.md`: enable I2C, set USB serial latency, udev rules, install the runtime (`pip install -e .`)
- [ ] Wire the BNO055 (3V3, GND, SDA = GPIO2, SCL = GPIO3) and test: `python3 mini_bdx_runtime/mini_bdx_runtime/raw_imu.py`
- [ ] Pair the Xbox One controller over Bluetooth

## Phase 5 — Configure servos (one at a time!)
- [ ] Connect a single servo to the Waveshare adapter, power it from the pack
- [ ] `python configure_motor.py --id <id>` for each ID in [SERVO_MAP.md](SERVO_MAP.md)
- [ ] When the servo moves to zero, fit the horn as aligned as you can
- [ ] Label every servo with its ID and joint name

## Phase 6 — Mechanical assembly (follow the assembly guide)
- [ ] Trunk: bearings + M3 inserts in `trunk_bottom`; join to `trunk_top` with 2 × M3x10; mount the middle motor
- [ ] Feet: TPU sole + PLA bottom (2 × M3x6), foot switches press-fit, ankle servo with driver side toward `foot_top`
- [ ] Legs: knee-to-ankle sheets, leg spacers (inserts on both sides)
- [ ] Hips: roll motor top/bottom, roll-to-pitch parts
- [ ] Neck and head: neck sheets, head pitch/yaw/roll parts, bearing, Pi Zero mounted in the head
- [ ] Body panels and battery pack
- [ ] Blue Loctite 243 on every metal-on-metal screw. **Never** on plastic screws
- [ ] Move every joint by hand and check cables have slack

## Phase 7 — First power and calibration
- [ ] Robot on a stand, feet off the ground
- [ ] `python3 scripts/check_motors.py`: all 14 respond
- [ ] Check the IMU frame: `scripts/imu_server.py` on the robot + `scripts/imu_client.py --ip <robot_ip>` on your PC
- [ ] Create `duck_config.json` from `example_config.json` (IMU orientation, optional features)
- [ ] `python find_soft_offsets.py`: find and save joint offsets; record them in SERVO_MAP.md

## Phase 8 — Walk!
- [ ] Copy `BEST_WALK_ONNX_2.onnx` to the Pi
- [ ] `python v2_rl_walk_mujoco.py --onnx_model_path <path>/BEST_WALK_ONNX_2.onnx`
- [ ] First steps on a flat floor with a hand ready to catch it
- [ ] Drive it with the Xbox controller

## Phase 9 — Make it your own (optional)
- [ ] Add expression features: eye LEDs, antennas (SG90), speaker, camera (see the Pi pin map in the assembly guide)
- [ ] Train your own policy with `upstream/playground` (needs a PC with an NVIDIA GPU)
- [ ] Modify the design in Onshape: paint, accessories, your own head
