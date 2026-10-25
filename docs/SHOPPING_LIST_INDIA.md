# Shopping list — India (prices checked 2026-10-25)

Prices change often. Check the final checkout total, including GST and shipping, before ordering.
Assumes ₹88 ≈ $1.

## Recommended route: official kit + local UNO Q + local filament

| Item | Where | Price | Notes |
| --- | --- | ---: | --- |
| XGO-Duck electronics kit (15 servos, driver board, 4000 mAh battery, charger, cables, screws, bearings) | [shop.xgorobot.com](https://shop.xgorobot.com/products/xgo-duck-biped-robot-electronics-kit-arduino-uno-q) | $352 ≈ ₹31,000 + shipping + customs | Covers everything except the UNO Q. No returns after shipping. Ask them for the shipping quote to India |
| Arduino UNO Q 2 GB (ABX00162) | [ElectroPi](https://www.electropi.in/official-arduino-uno-q-single-board-computer-abx00162) | ₹4,417 + 18% GST ≈ ₹5,210 | Cheapest found |
| ↳ alternative | [Crazypi](https://www.crazypi.com/official-arduino-uno-q-ai-linux-sbc-india) | ₹5,800 | |
| ↳ alternative | [Amazon.in](https://www.amazon.in/Arduino-UNO-ABX00162-microprocessor-Microcontroller/dp/B0FVLQLMSV) | ₹5,949 | Easy returns |
| PLA+ 1 kg (body) | Amazon.in: NFIL3D HS PLA+ / WOL3D PLA PRO+ | ₹669–849 | 1 spool is probably enough; buy 2 if you expect reprints |
| TPU 95A (soles, beak) | [Robocraze — Anycubic TPU 95A 1 kg](https://robocraze.com/products/anycubic-tpu-95a-black-1kg-flexible-1-75mm-3d-printer-filament) | ₹2,799 | Only a few grams are needed; a 250–500 g spool is cheaper if you can find one |

**Estimated total: about ₹40,000–48,000 including import duty**, depending on shipping and customs.

## DIY route (source parts yourself)

Only worth it if a kit shipment to India is too expensive or not possible.

| # | Part | Qty | Best option found | Price | Notes |
| ---: | --- | ---: | --- | ---: | --- |
| 4 | **Feetech HD-1910-C001** servo | 15 | [eBay 15-pc lot](https://www.ebay.com/itm/880036538936) / [ArmDojo 15-servo set](https://armdojo.com/products/feetech-hd-1910-c001-coreless-servo-microduck) | $320–420 ≈ ₹28,000–37,000 + import | Not stocked by Indian shops. Do **not** substitute STS3215 (sold by Evelta at ₹2,224): it is bigger and won't fit the printed parts |
| 2 | Robot driver board | 1 | [Luwu store](https://shop.xgorobot.com/products/robot-driver-board) | $20 ≈ ₹1,760 + shipping | Only source |
| 5 | 2S 18650 pack 7.4/8.4 V, > 2500 mAh, > 3C | 1 | [Robu Pro-Range 4000 mAh 2S2P](https://st.robu.in/product/pro-range-18650-li-ion-4000mah-2s-7-4v-3c-2s2p) | ₹599 | Has an Amass/DC connector, **not XH2.54**. You'd need to fit an XH2.54 plug with the correct polarity |
| 6 | 8.4 V 2S charger | 1 | [Robu Pro-Range 8.4 V 2 A](https://st.robu.in/product/pro-range-battery-charger-2s-li-ion-8-4v-2a-with-dc-5-5mm-2-5mm-male-plug) | ₹449 | Has a 5.5 × **2.5** mm plug, not 2.1 mm. Check it fits the board's jack |
| 3 | AMP 3-pin servo cable | 15 | Usually included with the servos | — | |
| 7–9 | M2 × 6 CSK, M2.3 × 8, M3 × 16 screws | 204 / 6 / 4 | Amazon.in M2/M2.5/M3 self-tapping assortment | ~₹400–800 | Check head shapes against the fastener guide |
| 10 | Bearing 10 × 15 × 3 (6700 open) | 10 | AliExpress 6700 10-packs, or IndiaMART | ~₹50–150 each | Thin-section bearings are rare in Indian retail |
| 11 | Bearing 16 × 22 × 4 (MR2216 / SMR2216) | 11 | AliExpress "16x22x4" | ~₹100–200 each | Non-standard size; search by dimensions |

DIY usually costs **more** than the kit once you add the servo lot, separate shipments and customs.

## Customs tip
Courier imports into India pay basic customs duty + IGST, often 30–40%+ for this kind of item. Confirm with the courier (DHL/FedEx) before ordering, and keep the invoice.
