# MicroDuck Project

My build of a 3D-printed biped robot duck — 15 serial servos, an Arduino UNO Q brain, and RL-trained walking policies.

This build follows **[XGO-Duck](https://github.com/LuwuDynamics/xgoduck_hardware)** by Luwu Dynamics, which is based on **[Microduck](https://github.com/pollen-robotics/microduck)** by Pollen Robotics. Upstream design files are linked as git submodules (not copied) so their own licenses and notices stay intact.

## Repository layout

| Path | What's in it |
| --- | --- |
| [`docs/BUILD_PLAN.md`](docs/BUILD_PLAN.md) | Phase-by-phase plan with checklists — start here |
| [`docs/SHOPPING_LIST.md`](docs/SHOPPING_LIST.md) | Parts to buy, with status tracking |
| [`docs/PRINT_TRACKER.md`](docs/PRINT_TRACKER.md) | Every printed part, copies and progress |
| [`docs/SERVO_MAP.md`](docs/SERVO_MAP.md) | Servo IDs, labels and calibration record |
| [`docs/BUILD_LOG.md`](docs/BUILD_LOG.md) | Dated notes, problems and fixes |
| `upstream/hardware` | STL parts, PCB files, assembly guide PDF (submodule) |
| `upstream/runtime` | UNO Q firmware + browser control app (submodule) |
| `upstream/rl` | Simulation and RL training (submodule) |

## Getting the upstream files

```bash
git clone --recurse-submodules https://github.com/yuvarajeshsp-cloud/<this-repo>.git
# or, in an existing clone:
git submodule update --init --depth 1
```

Key files once fetched:

- Assembly guide: `upstream/hardware/Assembly_Guide.pdf`
- STL parts: `upstream/hardware/structure/`
- Runtime app (Arduino App Lab project): `upstream/runtime/`

## The robot at a glance

| Subsystem | Part |
| --- | --- |
| Controller | Arduino UNO Q (Linux side runs ONNX policy + web UI, STM32 side runs the servo/IMU loop) |
| Actuators | 15 × Feetech 1910 serial servos (10 legs, 4 neck/head, 1 mouth) |
| Driver board | Luwu robot expansion board for UNO Q (power, servo bus, QMI8658A IMU) |
| Power | 8.4 V 18650 pack, XH2.54, > 2500 mAh, > 3C |
| Body | ~30 STL files, rigid filament + TPU soles/beak |

> ⚠️ When testing and tuning servos, avoid stalling them.
> ⚠️ The **old** expansion board revision swaps GND/SIGNAL on U3–U5 — see `upstream/hardware/PCBA/README.md` before powering.

## Credits

XGO-Duck by Luwu Dynamics, based on Microduck and microduck_rl by Pollen Robotics. Training uses mjlab and Rhoban BAM. This is a personal, non-commercial build; check `upstream/hardware/LICENSING.md` before redistributing any design files.
