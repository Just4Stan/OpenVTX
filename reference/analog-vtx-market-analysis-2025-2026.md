# Analog FPV VTX Market Analysis (2025-2026)

Research compiled March 2026 for open-source VTX design reference.

---

## 1. Current Top VTX Products

### Premium Tier ($25-40)

| Product | Power | Size | Weight | Connector | Protocol | Input V | Price |
|---------|-------|------|--------|-----------|----------|---------|-------|
| TBS Unify Pro32 HV | 25-1000mW | Compact standalone | ~6g | MMCX | SmartAudio, Crossfire, USB | 7-36V (2-6S) | ~$35-40 |
| TBS Unify Pro32 Nano | 25-500mW+ | Ultra-compact | ~2g | MMCX | SmartAudio, Crossfire | 7-36V | ~$30 |
| Rush Tank Solo | PIT/25/400/800/1000/1600mW | 37x24x6.7mm | 12g | MMCX | SmartAudio V2.1 | 7-36V (2-6S) | ~$30-35 |

### Mid-Range Tier ($15-25)

| Product | Power | Size | Weight | Connector | Protocol | Input V | Price |
|---------|-------|------|--------|-----------|----------|---------|-------|
| Rush Tank Mini | 25-800mW | 20x20mm | ~4g | MMCX | SmartAudio | 7-36V | ~$20 |
| HGLRC Zeus VTX PRO 1.6W | PIT/25/400/800/1600mW | 25x37x6.5mm | 13g | MMCX | SmartAudio | 7-36V | ~$22 |
| HGLRC Zeus 800mW | PIT/25/100/200/400/800mW | 37x37x5mm (20x20/30x30) | 4.8g | MMCX | SmartAudio | 7-36V | ~$18 |
| SpeedyBee TX800 | 25-800mW | 20x20mm | 2.6g | u.FL | SmartAudio | 5V only | ~$15 |
| SpeedyBee TX1600 Ultra | 25-1600mW | Standalone | ~10g | MMCX | SmartAudio | 7-36V | ~$22 |
| RDQ Mach 3 | 25-1000mW | 20x20mm | ~4g | MMCX/u.FL | SmartAudio | 7-36V | ~$20 |

### Budget Tier ($8-15)

| Product | Power | Size | Weight | Connector | Protocol | Input V | Price |
|---------|-------|------|--------|-----------|----------|---------|-------|
| AKK Race | 25-200mW | Compact | ~2g | u.FL | SmartAudio | 5V | ~$10 |
| Eachine Nano VTX V3 | 25-400mW | Nano | ~2g | u.FL | SmartAudio/Tramp | 5V | ~$10 |
| Eachine TX805 | 25-800mW | Compact | ~5g | SMA | SmartAudio | 7-24V | ~$13 |
| BetaFPV A03 | 25-400mW | 16x16/20x20 | ~2g | u.FL | OpenVTx/SmartAudio | 5V | ~$12 |

### Micro/Whoop Tier

| Product | Power | Size | Weight | Connector | Protocol | Price |
|---------|-------|------|--------|-----------|----------|-------|
| Rush Tiny Tank | 25-350mW | 12.5x17mm | 1.4g | u.FL | SmartAudio | ~$15 |
| HGLRC Zeus Nano | 25-350mW | 16x16/20x20/25.5x25.5 | ~1.5g | IPEX/u.FL | SmartAudio | ~$12 |

### High-Power / Long-Range

| Product | Power | Connector | Notes | Price |
|---------|-------|-----------|-------|-------|
| Foxeer Reaper Extreme | 2500mW | SMA | Includes fan/heatsink, massive heat | ~$35 |
| AKK Race Ranger 1.6W | PIT/25/400/800/1600mW | MMCX | Used in military FPV drones | ~$20 |
| AKK X2 Ultimate | 25-1200mW | MMCX | Long-range budget option | ~$18 |

### Key Observations
- TBS Unify Pro32 is the "gold standard" -- clean signal, honest power ratings, but most expensive
- Rush has eaten significant market share with competitive quality at lower prices
- HGLRC Zeus line dominates budget-to-mid segment
- Chinese manufacturers (AKK, HGLRC, SpeedyBee) have driven prices down dramatically
- The 800mW sweet spot serves 90% of pilots; 1.6W is niche for long-range

---

## 2. Feature Comparison: Premium vs Budget

| Feature | Premium (TBS/Rush) | Budget (AKK/Eachine) |
|---------|-------------------|---------------------|
| Signal cleanliness | Clean, minimal bleed to adjacent channels | Often "dirty," interferes with nearby pilots |
| Power accuracy | Honest rated output | Often overstated by 20-50% |
| Frequency accuracy | Precise, tight tolerance | Can drift, especially when hot |
| Build quality | Aluminum enclosures, conformal coating | Bare PCB, no protection |
| Thermal management | Integrated heatsink/case | None or minimal |
| Pit mode | Reliable, <1mW | Often unreliable or absent |
| Connector quality | Solid MMCX | Cheap u.FL that detaches in crashes |
| Firmware updates | USB/SmartAudio updates | Usually none |
| Audio/microphone | Built-in mic on some | Rarely included |
| Voltage range | Wide (2-6S direct) | Often 5V only (needs external BEC) |

---

## 3. Common Complaints from Pilots

### Signal Quality
- Cheap VTXes bleed into adjacent channels, ruining group flying / races
- Electrical noise from ESCs causes video noise on throttle-up
- Power filtering on budget VTXes is inadequate
- Actual output power often doesn't match rated specs

### Heat
- VTXes overheat on the bench without airflow (especially >400mW)
- Overheating causes reduced range, video degradation, and permanent damage
- High-power VTXes (1W+) get dangerously hot even in flight
- No thermal shutdown protection on most units

### Connectors
- MMCX connectors deemed "the worst" by some pilots -- can be pulled out in crashes
- u.FL connectors pop off in flight or after crashes
- SMA is robust but too large/heavy for modern builds
- No universally loved connector exists

### Reliability
- Powering VTX without antenna attached = instant death for most units
- Water/moisture ingress kills VTXes
- Crash damage is common, especially to antenna connections
- Budget VTXes (especially Eachine) have poor longevity

### Configuration
- SmartAudio and Tramp are proprietary and sometimes flaky
- Protocol detection can fail, leaving VTX unconfigurable
- No standardized way to configure without FC (standalone config)
- Button-based channel/power selection is tedious and error-prone

### Size/Weight
- High-power VTXes are too large for tight builds
- Mounting pattern variety means adapters are often needed
- Stack-mount VTXes add height to already tall FC stacks

---

## 4. Power Levels

### Common Power Steps
| Level | Typical Use | Range (approx) |
|-------|-------------|-----------------|
| PIT (<1mW) | Pits at races, bench testing | ~5m |
| 25mW | Indoor, whoops, racing pits | ~200m |
| 200mW | Park flying, casual freestyle | ~500m |
| 400mW | Freestyle, general purpose | ~1km |
| 800mW | Long-range freestyle, penetration | ~2-3km |
| 1000mW (1W) | Long-range | ~3-5km |
| 1600mW (1.6W) | Long-range dedicated | ~5km+ |
| 2000-3000mW | Extreme long-range (AKK) | ~10km+ |

### What Pilots Actually Use
- **Racing**: 25mW (mandatory at events) with pit mode
- **Freestyle**: 400-800mW most common
- **Long-range**: 800mW-1.6W
- **Whoops/micro**: 25-200mW
- **Most common default**: 400mW -- good balance of range and heat

### Regulatory Notes
- US: 1W (1000mW) limit without HAM license on 5.8GHz
- EU: 25mW limit in many countries (widely ignored in practice)
- HAM license allows higher power in most jurisdictions
- Many VTXes ship with "US" and "international" firmware variants

---

## 5. Form Factors

### Mounting Patterns
| Pattern | Use Case | Notes |
|---------|----------|-------|
| 16x16mm | Micro/whoop builds | Tiniest builds, usually low power |
| 20x20mm | Standard racing/freestyle | Most popular for 3-5" quads |
| 25.5x25.5mm | Some racing frames | Less common, legacy |
| 30x30mm (30.5x30.5) | Larger builds, long-range | Higher power VTXes |
| Standalone (no stack) | Anywhere, zip-tied/taped | Rush Tank Solo style, aluminum case |

### Antenna Connectors
| Type | Size | Durability | Mating Cycles | Use Case |
|------|------|------------|---------------|----------|
| SMA/RP-SMA | Large | Excellent (500+) | 500+ | Legacy, long-range, ground stations |
| MMCX | Medium | Good | ~500 | Standard for 5" builds, replacing SMA |
| u.FL (IPEX) | Tiny | Poor | ~30 | Micros/whoops only, fragile |

### Connector Trends
- MMCX is now the dominant standard for 5" builds
- u.FL accepted only on micro/whoop builds where weight matters
- SMA being phased out on quad VTXes but still used on ground-side
- Some pilots solder antenna pigtails directly to avoid connector failures

---

## 6. VTX Control Protocols

### SmartAudio (TBS)
- **Developer**: Team BlackSheep
- **Versions**: V1.0, V2.0, V2.1, Lite
- **Connection**: Single-wire (TX pin of UART)
- **Features**: Change channel, band, power, pit mode via Betaflight OSD
- **Market share**: Dominant -- most VTXes support this
- **Issues**: Proprietary, version fragmentation, power levels use coded values (not mW)

### IRC Tramp (ImmersionRC)
- **Developer**: ImmersionRC
- **Connection**: Serial (UART TX+RX)
- **Features**: Same as SmartAudio but sends power in mW directly
- **Market share**: Declining, mostly ImmersionRC and some budget VTXes
- **Issues**: Less widely supported, dying out

### MSP (Betaflight native)
- **Developer**: Betaflight / OpenVTx
- **Connection**: Serial UART
- **Features**: Vendor-neutral, self-configuring VTX tables, auto-detection
- **Status**: Preferred protocol from Betaflight 4.4+ and OpenVTx 0.2+
- **Advantage**: No proprietary lock-in, VTX can push its own capability table to FC

### ExpressLRS Serial VTX
- **Connection**: Via ELRS receiver serial passthrough
- **Features**: Control VTX settings through ELRS link
- **Status**: Growing adoption

### Recommendation for Open-Source Design
**MSP should be the primary protocol**, with SmartAudio V2.1 and Tramp as fallback for legacy compatibility. MSP is vendor-neutral, self-describing, and the direction Betaflight is heading.

---

## 7. OSD Integration

### Current State
- **FC-integrated OSD is the universal standard** -- MAX7456/AT7456E chip on the FC overlays telemetry onto analog video
- Standalone OSD boards (MinimOSD) are dead/legacy
- VTX with built-in OSD is rare and generally unwanted -- pilots want FC OSD
- The VTX just passes video through; OSD overlay happens on the FC

### What Pilots Want
- VTX should NOT have built-in OSD (adds cost, complexity, potential failure)
- Clean video passthrough from camera to antenna
- FC handles all OSD via MAX7456/AT7456E chip
- VTX status (channel, power, pit mode) displayed via Betaflight OSD menu

### Exception: tinyFINITY / All-in-One
- fishpepper's open-source tinyFINITY combines VTX + OSD on 16x16mm board
- Uses STM32F3 + RTC6705, software OSD (35 chars x 13 lines, 8 gray levels)
- Draws only 10mA for OSD vs 120mA for MAX7456
- Niche: ultra-micro builds where FC doesn't have OSD chip

---

## 8. Pit Mode & Race Features

### Importance: Critical for Racing
- **Pit mode reduces output to <1mW** (~0.001mW, ~5m range)
- Without pit mode, powering up a VTX in the pits blinds other pilots on adjacent channels
- Required for organized racing (MultiGP, etc.)
- Two variants:
  - **POR (Pit Out of Range)**: Transmits on fixed frequency 5584 MHz
  - **PIR (Pit In Range)**: Transmits on set frequency at minimum power

### Race Features Pilots Want
- Reliable pit mode on boot (not just via SmartAudio command)
- Pit mode switch on transmitter (Betaflight mode switch)
- Quick power switching without VTX restart
- Clean signal that doesn't bleed into adjacent Raceband channels
- Accurate frequency output (no drift under heat)

### Raceband
- 8 channels spaced 37 MHz apart: 5658, 5695, 5732, 5769, 5806, 5843, 5880, 5917 MHz
- Allows 6-8 pilots to fly simultaneously without interference
- Cheap VTXes with dirty signals reduce usable pilot count

---

## 9. Heat Management

### The Problem
- VTXes at 800mW+ generate significant heat
- PA (power amplifier) stage is the primary heat source
- Operating above 80C degrades performance and shortens lifespan
- On the bench with no airflow, high-power VTXes can fail in minutes

### Current Solutions
| Approach | Used By | Effectiveness |
|----------|---------|---------------|
| Aluminum enclosure as heatsink | Rush Tank Solo, TBS Unify | Good -- doubles as protection |
| Clip-on aluminum heatsink | SpeedyBee TX800, aftermarket | Moderate |
| Thermal pad to frame | DIY | Moderate -- uses carbon frame as sink |
| Active cooling fan | Foxeer Reaper Extreme | Best, but adds weight/complexity |
| Thermal throttling | TBS Crossfire Sixty9 | Reduces power when hot |
| Bare PCB (nothing) | Most budget VTXes | Poor -- relies entirely on airflow |

### Design Recommendations
- Aluminum enclosure with thermal pad coupling to PA is the best passive approach
- Exposed copper pad on bottom of PCB for frame-mount heat sinking
- Thermal shutdown protection should be standard (it currently isn't on most)
- Auto-throttle power when temperature exceeds safe threshold
- Temperature telemetry via MSP/SmartAudio would be valuable

---

## 10. Price Points Summary

| Segment | Price Range | Typical Products |
|---------|-------------|-----------------|
| Ultra-budget | $8-12 | AKK Race, Eachine Nano, no-name clones |
| Budget | $12-18 | HGLRC Zeus Nano, BetaFPV A03, SpeedyBee TX800 |
| Mid-range | $18-25 | Rush Tank Mini, HGLRC Zeus 800/1.6W, SpeedyBee TX1600 |
| Premium | $25-40 | TBS Unify Pro32 HV, Rush Tank Solo |
| Extreme | $35-50 | Foxeer Reaper Extreme, high-power niche |

### Key Pricing Observations
- Analog VTX prices have collapsed -- $15-20 gets a very capable 800mW unit
- TBS commands a premium based on reputation and signal quality
- Chinese manufacturers have made high power (1.6W) available for ~$20
- The entire analog VTX is often the cheapest component in a build
- Digital VTX starts at $50+ (HDZero) to $100+ (DJI/Walksnail)

---

## 11. Frequency Agility

### Standard Bands (5.8GHz ISM)
| Band | Channels | Frequency Range | Notes |
|------|----------|-----------------|-------|
| A (Boscam) | 8 | 5865-5945 MHz | Legacy |
| B (Boscam) | 8 | 5733-5866 MHz | Legacy |
| E (Lumenier) | 8 | 5705-5945 MHz | |
| F (ImmersionRC/FatShark) | 8 | 5740-5880 MHz | Popular |
| R (Raceband) | 8 | 5658-5917 MHz | Racing standard, 37MHz spacing |

### Channel Counts
- **40-channel**: Standard (5 bands x 8 channels) -- A, B, E, F, R
- **48-channel**: Adds extra bands (D, U, O, L, H) -- some outside legal allocations
- **37-channel (US locked)**: Only ITU Region 2 legal channels (5650-5925 MHz)
- **Unlocked**: All 48+ channels available, user responsibility for legality

### Regulatory Bands
- **US (ITU Region 2)**: 5.650-5.925 GHz -- Raceband fits, some upper A/B channels do not
- **EU**: More restrictive, 25mW power limits in many countries
- **L/U/O bands**: Often fall outside legal allocations; avoid for a legal product

### Design Recommendation
- Support all 40 standard channels (A/B/E/F/R) minimum
- 48-channel unlocked mode as optional firmware feature
- Default to region-appropriate channel/power limits
- Raceband is the most important band for competitive pilots

---

## 12. Reliability Issues / Common Failure Modes

### Ranked by Frequency
1. **No antenna = dead VTX** -- Running without antenna load reflects power back into PA, burns it instantly. No consumer VTX has antenna detection/protection.
2. **Crash damage to antenna connector** -- u.FL pops off; MMCX can be ripped from pad
3. **Overheating** -- Prolonged high-power bench operation without airflow
4. **Water/moisture ingress** -- Rain, dew, grass landings
5. **Solder joint failure** -- Vibration cracks joints, especially on signal wires
6. **Voltage spike damage** -- LiPo voltage spikes on plug-in, inadequate input filtering
7. **ESD damage** -- Static discharge during handling
8. **Firmware corruption** -- SmartAudio misconfiguration leaving VTX in broken state

### What's Missing in Current Designs
- **No antenna VSWR detection** -- Could protect PA from no-antenna condition
- **No thermal shutdown** -- VTX runs until it dies
- **No reverse polarity protection** on most budget units
- **No brownout protection** -- Voltage sag during flight causes VTX reset/reboot
- **No self-diagnostic capability** -- No way to know if VTX is degraded

---

## 13. What's Missing -- Features Pilots Wish Existed

### Hardware
- **Antenna detection / VSWR protection** -- Refuse to transmit (or limit power) if no antenna detected
- **Thermal shutdown / auto-throttle** -- Reduce power before burning out
- **Temperature telemetry** -- Report VTX temp via MSP to OSD
- **Better connector than MMCX** -- Something crash-resistant but still swappable
- **Conformal coating standard** -- Weather resistance on all units
- **Integrated LC filtering** -- Clean power input without external caps
- **On-board DVR** -- Record analog video locally (exists on some digital, not analog)
- **Dual-band (5.8GHz + 1.3GHz)** -- Niche but desired for long-range
- **True power calibration** -- Factory-calibrated output power per channel

### Firmware / Software
- **Open-source firmware** -- OpenVTx exists but limited hardware support, last release Oct 2022
- **MSP as primary protocol** -- Self-describing VTX tables, no proprietary lock-in
- **Web-based configurator** -- USB-C direct config without Betaflight
- **Per-channel power calibration tables** -- Compensate for frequency-dependent PA gain
- **Spectrum analyzer mode** -- Use VTX receiver chain to scan 5.8GHz band
- **Smart power management** -- Auto-reduce power near home, increase at range
- **Blackbox-style logging** -- Record VTX state (temp, power, channel) for debugging

### Quality of Life
- **Standardized mounting** -- One board that fits 16x16, 20x20, and 25.5x25.5
- **LED status indicators** -- Clear indication of channel, power, and pit mode
- **Audible beeper** -- Help find downed quad (some Rush models have mic but no beeper)
- **Boot-to-pit-mode** -- Always start in pit mode for race safety

---

## 14. Analog vs Digital Trend

### Analog Is Still Relevant For:
- **Racing** -- Cheapest, lightest, lowest-latency (though HDZero 540p@90fps now matches at 4ms)
- **Whoops/micros** -- Weight matters; analog VTX can be <2g vs digital at 5-10g+
- **Budget builds** -- Complete analog video system for ~$70 (goggles + VTX + camera)
- **Military/disposable drones** -- Ukraine conflict drives massive demand for cheap analog VTX
- **Training/beater quads** -- Cheap enough to not care about crashes
- **Legacy pilots** -- Huge installed base of analog goggles

### Digital Is Winning For:
- **Freestyle** -- Image quality matters for enjoyment
- **Cinematic** -- HD recording from goggles
- **Long-range** -- Digital error correction outperforms analog at range edges
- **New pilots** -- Digital is the default recommendation for newcomers in 2026

### Market Share Trend
- Analog declining but not dead; still ~30-40% of new builds (est. 2026)
- HDZero gaining in racing due to low latency + HD
- DJI O3/O4 and Walksnail dominate freestyle/cinematic
- OpenIPC emerging as open-source digital alternative
- Military demand (Ukraine) keeps analog production volumes high

### Implications for Open-Source Analog VTX
- There is a viable market, especially for:
  - Racing (cost-sensitive, weight-sensitive)
  - Military/commercial disposable drones
  - Open-source/hackable community
  - Education and DIY
- The design should optimize for: low cost, reliability, clean signal, light weight
- Don't try to compete with digital on image quality -- compete on cost, weight, openness, and reliability

---

## 15. Existing Open-Source VTX Projects

### OpenVTx (Firmware Only)
- **Repo**: github.com/OpenVTx/OpenVTx
- **Status**: Last release v0.2.0 (October 2022) -- appears stalled
- **Features**: MSP + SmartAudio + Tramp auto-detection, race mode (boot to pit)
- **Hardware**: EWRF E7082VM (V1/V2) at 500mW max, limited board support
- **Language**: C (75%) / Python (25%)
- **Gaps**: Limited hardware support, no active development, no high-power boards

### tinyFINITY (Full Hardware + Firmware)
- **Author**: fishpepper.de
- **Hardware**: STM32F3 + RTC6705, 16x16mm PCB
- **Features**: Software OSD (35x13 chars, 8 gray levels, 10mA draw), full open-source
- **Limitations**: Low power only (~20mW from RTC6705 internal PA), no external PA, micro-only

### OpenHD
- **Focus**: Digital FPV (not analog)
- **Relevance**: Shows community appetite for open-source FPV video

---

## 16. Core Chipsets Used in Analog VTXes

### RF Transmitter
- **RTC6705 (RichWave)** -- The universal 5.8GHz FM transmitter IC
  - Built-in VCO, PLL, modulator
  - Internal PA: +13dBm (~20mW) max
  - SPI-programmable frequency
  - 3.3V supply, 40-pin QFN
  - Every analog VTX uses this or its variants (RTC6705SP)

### Power Amplifiers (External)
- **SKY85728** (Skyworks) -- Common in mid-range VTXes
- **SE5004L** (Skyworks) -- Used in higher-power designs
- **RFX2401C** -- Budget PA option
- Various Chinese-made PAs for ultra-budget units
- PA selection determines max output power, efficiency, and spectral cleanliness

### Microcontrollers (for protocol handling)
- **STM32F0/F1/F3** -- Used in OpenVTx-compatible boards
- **EFM8** (SiLabs) -- Used in some TBS products
- Many budget VTXes use simple logic or small 8-bit MCUs

---

## 17. Design Specification for "Ultimate Open-Source Analog VTX"

Based on this market analysis, here is what the ideal open-source analog VTX would look like:

### Target Specs
| Parameter | Specification | Rationale |
|-----------|--------------|-----------|
| Output power | PIT / 25 / 200 / 400 / 800mW (1W stretch) | Covers all use cases; 800mW is the sweet spot |
| Input voltage | 7-36V (2-6S direct) | No external BEC needed |
| 5V output | 5V @ 1A regulated out | Power camera and other accessories |
| Frequency | 40ch minimum (A/B/E/F/R), 48ch unlocked option | Raceband essential |
| Control protocol | MSP primary, SmartAudio V2.1 + Tramp fallback | Future-proof + legacy compatible |
| Mounting | 20x20mm primary, breakout/adapter for 25.5 and 30x30 | 20x20 is the standard |
| Antenna connector | MMCX primary, u.FL variant for micro builds | MMCX is the current standard |
| Weight | <5g (board only), <12g (with enclosure) | Competitive with Rush Tank Mini |
| Thermal | Aluminum enclosure as heatsink, thermal pad to PA | Proven approach (Rush Tank Solo) |
| Audio | Built-in AGC microphone | Nice-to-have, pilots like hearing motors |
| Firmware | Open-source (OpenVTx-based or new), USB-C config | Key differentiator |
| MCU | RP2040 or STM32 | RP2040 aligns with your toolchain |

### Safety Features (Differentiators)
| Feature | Implementation |
|---------|---------------|
| Antenna detection | VSWR sensing on PA output; limit to 25mW if no antenna |
| Thermal protection | Thermistor on PA; auto-throttle power at 70C, shutdown at 85C |
| Temperature telemetry | Report via MSP to Betaflight OSD |
| Boot-to-pit | Always start in pit mode; require explicit power-up command |
| Reverse polarity protection | MOSFET-based on input |
| Brownout hold | Capacitor bank to maintain clean shutdown on voltage sag |

### Bill of Materials Core
| Component | Part | Notes |
|-----------|------|-------|
| RF TX | RTC6705SP | Universal 5.8GHz FM TX IC |
| PA | SKY85728 or SE5004L | Determines max power; needs evaluation |
| MCU | RP2040 | Dual-core, PIO for protocol handling |
| Regulator | TPS62xxx series | High-efficiency buck for 2-6S input |
| Connector | MMCX | Standard, pigtail to SMA for external antenna |

---

## Sources

- [Oscar Liang - Choosing the Best VTX](https://oscarliang.com/video-transmitter/)
- [Oscar Liang - FPV System Comparison 2026](https://oscarliang.com/fpv-system/)
- [Oscar Liang - 5.8GHz FPV Channels](https://oscarliang.com/fpv-channels/)
- [Oscar Liang - SmartAudio/Tramp VTX Control](https://oscarliang.com/smartaudio-tramp-vtx-control-vtxtables/)
- [Oscar Liang - SpeedyBee TX800 Review](https://oscarliang.com/speedybee-tx800/)
- [Oscar Liang - SpeedyBee TX1600 Ultra Review](https://oscarliang.com/speedybee-tx1600-ultra-vtx/)
- [Oscar Liang - Rush VTX Lineup Review](https://oscarliang.com/rush-vtx-tank-plus-race-mini-tiny/)
- [Joshua Bardwell FPV Shopping List - Analog](https://www.fpvknowitall.com/fpv-shopping-list-goggles-video-transmitters-and-cameras/)
- [GetFPV - FPV Antenna Connector Guide](https://www.getfpv.com/learn/fpv-essentials/fpv-drone-antenna-connector/)
- [GetFPV - FPV Frequency Chart](https://www.getfpv.com/learn/fpv-essentials/fpv-frequency-reference-chart/)
- [OpenVTx GitHub](https://github.com/OpenVTx/OpenVTx)
- [fishpepper.de - tinyFINITY Open Source VTX](https://fishpepper.de/2019/03/11/tinyosd-tinyfinity-a-tiny-opensource-video-tx-with-full-graphic-osd/)
- [RSL FPV - VTX Power Levels Explained](https://rslfpv.com/fpv-vtx-power-levels-25mw-vs-200mw-vs-800mw-explained/)
- [RSL FPV - VTX Signal Cleanliness](https://rslfpv.com/how-to-evaluate-fpv-vtx-power-output-and-signal-cleanliness/)
- [RSL FPV - Pit Mode Explained](https://rslfpv.com/what-is-pit-mode-in-vtx-and-when-should-you-use-it/)
- [Unmanned Tech - SmartAudio Guide](https://blog.unmanned.tech/smart-audio-vtx/)
- [Unmanned Tech - SmartAudio in Betaflight 4.5+](https://blog.unmanned.tech/the-ultimate-guide-to-smartaudio-vtx-control-in-betaflight-4-5/)
- [Betaflight VTX Documentation](https://www.betaflight.com/docs/wiki/getting-started/hardware/vtx)
- [WREKD - VTX Comprehensive Guide](https://wrekd.com/pages/a-comprehensive-guide-to-video-transmitters-vtx-for-fpv-drones)
- [AOS RC - VTX Performance Testing](https://www.aos-rc.com/aos-labs/vtx-performance)
- [RichWave RTC6705 Datasheet](https://wildlab.org/wp-content/uploads/2015/07/RTC6705-DST-001.pdf)
- [GEPRC - Common VTX Problems](https://geprc.com/docs/the-common-problems-of-vtx-and-solution/)
- [My Racing Drone - VTX Shopping Guide 2026](https://myracingdrone.com/fpv-video-transmitter/)
