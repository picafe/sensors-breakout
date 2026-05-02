# Sensors Breakout

Small 4-layer KiCad PCB that packs a RTC and several I²C and SPI sensors into a compact board (around 3x1.5 cm) for cheap assembly, lots of config options, and testing sensors.

---

## What it is

A breakout board of the **PCF8563 RTC**, **Sensirion SHT41** temperature/humidity sensor on an I²C bus. There is a **STMicro LSM6DSV** IMU connected over SPI with a 7-pin JST SH connector, and **QST QMC6309** magnetometer connected over I²C to the LSM6DSV's sensorhub with level shifting.

1.8 V power + logic for the RTC, temp sensor, and IMU, while keeping the magnetometer at 3.3 V via a LDO and BSS138 level shifter, so the design stays compatible with economic JLC PCBA (since QMC6309 is the only precise magnetometer offered with economic PCBA).

---

## Motivation

The board started as a quick PCF8563 test board which would go on a few of my other projects, and now is a general purpose board for testing sensors, with QWIIC-style connectors (JST SH).

---

## Features

| Area | Detail |
|------|--------|
| **RTC** | PCF8563 + crystal |
| **Temp/Humidity** | SHT41 (can be populated from a cheap breakout or omitted) |
| **Motion** | LSM6DSV 6-axis IMU |
| **Magnetometer** | QMC6309 |

- **Power:** 1.8 V rail for core I²C peripherals; 3.3 V LDO, VBAT input, and level shifting for magnetometer
- **Interface:** QWIIC-compatible connector; optional status LED with 3‑pad solder jumper (auto / manual pin / off)

---

## Current design

![PCB layout — routing](./images/kicad_7mpFMV2jHZ.png)

3D view:

![PCB 3D view](./images/kicad_PIgCup8CTn.png)

---
