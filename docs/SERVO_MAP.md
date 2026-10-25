# Servo map

Set IDs **one servo at a time** (duplicate IDs on the bus receive the same writes). Use the assembly guide p1 for exact placement within each group.

| ID | Group | Labelled | Mid reset | KpKd set | Calibrated | Notes |
| ---: | --- | :---: | :---: | :---: | :---: | --- |
| 10 | Left leg | [ ] | [ ] | [ ] | [ ] | |
| 11 | Left leg | [ ] | [ ] | [ ] | [ ] | |
| 12 | Left leg | [ ] | [ ] | [ ] | [ ] | |
| 13 | Left leg | [ ] | [ ] | [ ] | [ ] | |
| 14 | Left leg | [ ] | [ ] | [ ] | [ ] | |
| 20 | Right leg | [ ] | [ ] | [ ] | [ ] | |
| 21 | Right leg | [ ] | [ ] | [ ] | [ ] | |
| 22 | Right leg | [ ] | [ ] | [ ] | [ ] | |
| 23 | Right leg | [ ] | [ ] | [ ] | [ ] | |
| 24 | Right leg | [ ] | [ ] | [ ] | [ ] | |
| 30 | Neck / head | [ ] | [ ] | [ ] | [ ] | Keep secondary shaft |
| 31 | Neck / head | [ ] | [ ] | [ ] | [ ] | Keep secondary shaft |
| 32 | Neck / head | [ ] | [ ] | [ ] | [ ] | |
| 33 | Neck / head | [ ] | [ ] | [ ] | [ ] | |
| 34 | Mouth | [ ] | [ ] | [ ] | [ ] | Controlled separately from the policy |

Wiring: servo bus → UNO Q **D0/D1**, QMI8658 IMU → **D20/D21** (handled by the expansion board). Default gains in the UI: KP 5, KD 10.
