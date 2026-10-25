# Build plan

Work through the phases in order. Tick boxes as you go and add notes to [BUILD_LOG.md](BUILD_LOG.md).

## Phase 0 — Read before you buy
- [ ] Read `upstream/hardware/readme.md` and skim all 25 pages of `Assembly_Guide.pdf`
- [ ] Read `upstream/runtime/README.md` (servo setup + calibration)
- [ ] Decide: official electronics kit (everything except UNO Q) vs. sourcing parts individually
- [ ] Decide: include optional roller skates? (+3 printed parts, +4 screws, +8 small bearings)

## Phase 1 — Order parts
- [ ] Order everything in [SHOPPING_LIST.md](SHOPPING_LIST.md)
- [ ] Buy filament: rigid (PLA/PETG) + TPU for soles and beak
- [ ] On arrival, check the three screw types against `upstream/hardware/media/bom/fastener-shapes.svg`
- [ ] Confirm battery connector (XH2.54) and polarity match the board revision you received

## Phase 2 — Print
- [ ] Print a test piece first: one servo mount + one bearing seat. Check servo and bearing fit
- [ ] Use **4 walls, 13% gyroid infill**; follow the orientation image in `upstream/hardware/media/print-orientation-reference.png`
- [ ] Print everything in [PRINT_TRACKER.md](PRINT_TRACKER.md); check left/right parts
- [ ] Record printer, material and slicer settings in the build log

## Phase 3 — Electronics bring-up (on the bench, no robot yet)
- [ ] Inspect the expansion board against `upstream/hardware/PCBA/ArduinoUnoQ.pdf`; check for shorts with a multimeter
- [ ] Mount UNO Q on the expansion board
- [ ] Install Arduino App Lab, open `upstream/runtime`, click **Run** once
- [ ] On the UNO Q terminal: `python3 tools/prepare-bridge.py` then `sudo bash tools/router-2m.sh`, then Run again
- [ ] Open `http://<board-ip>:9527` and confirm the IMU shows **online**

## Phase 4 — Servo setup (one servo at a time!)
- [ ] For each of the 15 servos: connect alone → **Scan all IDs** → **Change ID** → **Reset Mid** → **Set KpKd**
- [ ] Label every servo physically with its ID (see [SERVO_MAP.md](SERVO_MAP.md))
- [ ] Set all-servo protection current (default field 1.5 A)

## Phase 5 — Mechanical assembly (follow the PDF)
- [ ] p1 — servo ID placement
- [ ] p2 — secondary shafts (keep on IDs 30, 31; don't remove output shafts)
- [ ] p3–5 — initial structure and cable routing (p3: don't install screws yet)
- [ ] p6–10 — legs (connect cables before joints close; left/right differ on p8)
- [ ] p11–15 — feet and TPU soles (check sole direction on p15)
- [ ] p16–20 — head/neck around IDs 32–34 (connect bottom cables before closing p17)
- [ ] p21 — adhesive step
- [ ] p22–23 — IDs 30/31 and M3 × 16 screws
- [ ] p24–25 — final assembly; move every joint by hand to check cable slack

## Phase 6 — First power and calibration
- [ ] Robot supported on a stand, joints clear
- [ ] Web UI shows **Servos online 15/15** and IMU online
- [ ] **Calibration**: hand-set each joint to mechanical center → **Set center & hold**; record in SERVO_MAP.md
- [ ] Back up the calibration file privately

## Phase 7 — Bring it to life
- [ ] **Inference only** (torque off) — watch that commanded motions look sane
- [ ] **Default pose** on the stand
- [ ] **Walk / get up** at low command on a flat clear floor
- [ ] Test **Torque off** behavior (robot will collapse — keep a hand ready)
- [ ] Try **Pick**, **Roulade**, head and mouth control

## Phase 8 — Make it your own (optional)
- [ ] Set up `upstream/rl` (uses `uv`), run the simulation
- [ ] Train/finetune a policy and export ONNX to the runtime
- [ ] Custom paint, eyes, accessories
