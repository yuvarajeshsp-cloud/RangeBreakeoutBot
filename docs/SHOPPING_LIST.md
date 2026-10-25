# Shopping list (India)

Prices checked 2026-10-25. They change often, so check the checkout total (GST + shipping) before ordering.
Quantities for screws and bearings come from the assembly guide and community builds; confirm against the [official BOM sheet](https://docs.google.com/spreadsheets/d/1gq4iWWHEJVgAA_eemkTEsshXqrYlFxXAPwO515KpCJc/edit?usp=sharing).

Status: `todo` → `ordered` → `received` → `checked`.

## Core electronics

| # | Part | Qty | Best option found | Approx. price (₹) | Status |
| ---: | --- | ---: | --- | ---: | --- |
| 1 | Feetech **STS3215 7.4 V 19 kg, 1:345 (C001)** | 14 | [Evelta](https://evelta.com/st3215-7-4v-19kg-1-345-gear-dual-axis-ttl-string-servo-motor/) ₹2,224 each incl. GST | 31,140 | todo |
| 2 | Waveshare Bus Servo Adapter (A) | 1 | Robu / Evelta / Amazon.in (search "Bus Servo Adapter (A)") | ~700–1,000 *(estimate)* | todo |
| 3 | Raspberry Pi Zero 2 W (+ header if not pre-soldered) | 1 | Official Raspberry Pi resellers (Robu, Robocraze, Thinkrobotics) | ~1,600–2,000 | todo |
| 4 | microSD card, 16–32 GB | 1 | Any | ~300 | todo |
| 5 | BNO055 IMU breakout | 1 | [Thinkrobotics](https://thinkrobotics.com/ar/products/9-dof-absolute-orientation-bno055-sensor) ₹1,500 / Adafruit at [Evelta](https://evelta.com/adafruit-industries/) ₹3,518 + GST | 1,500–4,150 | todo |
| 6 | Micro-switches (foot contact) | 4 | Robu / local | ~100 | todo |

## Power

| # | Part | Qty | Best option found | Approx. price (₹) | Status |
| ---: | --- | ---: | --- | ---: | --- |
| 7 | 18650 cell, high-drain (Molicel P28A) | 2 | [Hubtronics](https://hubtronics.in/battery-cells/molicel-inr18650-p28a) ~₹459 / [Robu](https://st.robu.in/?p=1230834) ₹529 | ~920 | todo |
| 8 | 2S 18650 holder (with midpoint lead for BMS) | 1 | Robu / local | ~100 | todo |
| 9 | 2S BMS, balanced, ≥ 5 A | 1 | [Robu generic BMS](https://robu.in/product-category/batteries/battery-chargers-and-accessories/bms-battery-management-system/generic-bms) | ~70–200 | todo |
| 10 | USB-C 2S (8.4 V) charging board | 1 | Robu / Amazon.in | ~150–300 *(estimate)* | todo |
| 11 | 5 V 3 A UBEC | 1 | Robu / drone shops | ~250–400 *(estimate)* | todo |
| 12 | Power switch (rocker) | 1 | Local | ~50 | todo |
| 13 | XT30 connector pair, silicone wire (red/black) | 1 set | Robu / drone shops | ~200 | todo |

## Mechanical

| # | Part | Qty | Best option found | Approx. price (₹) | Status |
| ---: | --- | ---: | --- | ---: | --- |
| 14 | 608ZZ bearing (8 × 22 × 7 mm) | check BOM | Amazon.in 10-pack ~₹215 | ~215 | todo |
| 15 | M3 brass heat-set inserts | ~100 | [Robu 50 pcs](https://robu.in/product/m3x12-mm-brass-insert-50pcs) ₹392, or IndiaMART | ~400–800 | todo |
| 16 | M3 screw assortment (M3x6, M3x10 and others) | 1 kit | Amazon.in | ~400 | todo |
| 17 | Loctite 243 (blue threadlocker) | 1 | Amazon.in | ~300 | todo |

## Filament and tools

| # | Part | Qty | Best option found | Approx. price (₹) | Status |
| ---: | --- | ---: | --- | ---: | --- |
| 18 | PLA / PLA+ 1 kg | 2 | NFIL3D / WOL3D on Amazon.in | 1,340–1,700 | todo |
| 19 | TPU 95A | 1 | [Robocraze Anycubic 1 kg](https://robocraze.com/products/anycubic-tpu-95a-black-1kg-flexible-1-75mm-3d-printer-filament) ₹2,799, or a smaller spool | 1,000–2,800 | todo |
| — | Soldering iron + insert tip, hex drivers (2, 2.5 mm), multimeter | — | Already own? | — | — |

## Optional

| Part | Qty | Approx. price (₹) |
| --- | ---: | ---: |
| Xbox One controller (Bluetooth) | 1 | ~4,500 (or use any BT gamepad supported by the runtime) |
| SG90 servos for antennas | 2 | ~200 |
| Eye LEDs, MAX98357A speaker amp + speaker, Pi camera | — | ~1,500 |

## Estimated total

**Core robot: about ₹41,000–46,000**, depending on the IMU and filament you pick. The servos are ~75% of it. Everything is available in India, so there's no customs.

Money-saving tips:
- Ask Evelta for a quantity quote on 14 servos
- Use a smaller TPU spool; only the two soles need it
- A generic BNO055 board works fine. Community builders report I2C glitches, fixed by using software I2C (`dtoverlay=i2c-gpio`)
