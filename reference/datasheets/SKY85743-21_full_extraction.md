# SKY85743-21 Full Datasheet Extraction
## Document 204720F, July 29, 2019, Skyworks Solutions

## Pinout (24-pin LGA, 3x5mm, top view)

| Pin | Name | Description |
|-----|------|-------------|
| 1 | GND | Ground |
| 2 | TX_IN | Transmit Input |
| 3 | GND | Ground |
| 4 | PA_EN | PA enable |
| 5 | GND | Ground |
| 6 | GND | Ground |
| 7 | GND | Ground |
| 8 | DET | Detector output |
| 9 | GND | Ground |
| 10 | C1 | Control pin 1 |
| 11 | GND | Ground |
| 12 | ANT | Antenna |
| 13 | C0 | Control pin 0 |
| 14 | RX_OUT | Switch RX output |
| 15 | GND | Ground |
| 16 | LNA_IN | LNA input |
| 17 | LNA_OUT | LNA output |
| 18 | GND | Ground |
| 19 | VDD | LNA supply voltage |
| 20 | GND | Ground |
| 21 | GND | Ground |
| 22 | VCC3 | PA third stage supply |
| 23 | VCC2 | PA second stage supply |
| 24 | VCC1 | PA first stage supply |
| 25 | GND | Exposed pad (thermal) |

## Absolute Maximum Ratings

| Parameter | Max |
|-----------|-----|
| VCC (all supplies) | 6.0V |
| Control pin voltage | 3.6V |
| **Input power TX_IN** | **+10 dBm** |
| Supply current | 800mA |
| Junction temp | 160°C |
| Theta_JC | 34°C/W |

## TX Mode Specs (VCC=5V, 25°C)

| Parameter | Min | Typ | Max |
|-----------|-----|-----|-----|
| Frequency | 5.15 | — | 5.925 GHz |
| Gain (small signal) | 32 | 34 | — dB |
| MCS0 HT20 Pout | 25 | **27** | — dBm |
| MCS7 Pout | 23 | 25 | — dBm |
| MCS9 Pout | 22 | 24 | — dBm |
| MCS11 Pout (-43dB DEVM) | 18 | 21 | — dBm |
| Current @ quiescent | — | 190 | 200 mA |
| Current @ +21dBm | — | 270 | 300 mA |
| Current @ +25dBm | — | 360 | 400 mA |
| Current @ +27dBm | — | 410 | 455 mA |
| 2nd harmonic @ +27dBm | — | -50 | -43 dBm/MHz |
| Input return loss | — | — | 9 dB |

**CW Psat estimate: +27 dBm typ (500mW), possibly +28-29 dBm (630-800mW)**
Based on MCS0 HT20 rating of +27dBm typ.

## Power Detector

| Parameter | Min | Typ | Max |
|-----------|-----|-----|-----|
| VDET @ +5dBm | 0.26 | 0.33 | 0.39 V |
| VDET @ +10dBm | 0.40 | 0.46 | 0.53 V |
| VDET @ +21dBm | 0.68 | 0.75 | 0.82 V |
| VDET @ +28dBm | 0.85 | 0.93 | 1.00 V |
| Slope | — | 21-26 | — mV/dB |
| Error (+10 to +28dBm) | — | — | 1.5 dB pk-pk |
| Output impedance | — | 100 | 220 ohm |

Logarithmic, temperature-compensated. 23dB dynamic range (+5 to +28 dBm).

## Control Truth Table

| Mode | PA_EN | C0 | C1 |
|------|-------|----|----|
| **TX to ANT** | **1** | **0** | **1** |
| RX LNA | 0 | 1 | 0 |
| RX bypass | 0 | 1 | 1 |
| All off | 0 | 0 | 0 |

For TX-only: tie PA_EN=VCC, C1=VCC, C0=GND.

## Decoupling (from eval board BOM)

| Pin | Cap | Value |
|-----|-----|-------|
| VCC1 (24) | C6+C9 | 2x 100nF |
| VCC2 (23) | C1 | 10µF |
| VCC3 (22) | C3 | 100nF |
| VDD (19) | C2 | 1nF |
| TX_IN (2) | C7 | 10pF DC block |
| DET (8) | C5 | 10pF |
| LNA_OUT (17) | C8 | 10pF DC block |

## Critical Design Notes

- TX_IN is DC-shorted to GND internally — use 10pF DC blocking cap
- ANT is DC-blocked internally — no external cap needed
- Max input power +10dBm — RTC6705 outputs +13dBm, MUST attenuate
- Supply: 5V (4.2-5.5V range) — needs separate 5V rail, NOT 3.3V
- Thermal pad must have via array (0.3mm drill, 0.6mm pitch, resin-filled)
