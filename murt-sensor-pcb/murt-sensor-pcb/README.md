# MURT Sensor Interface & Monitoring PCB

Sensor interface and monitoring board for the **McMaster Underwater Robotics Team (MURT)** ROV/submarine platform. This board collects environmental and vehicle-state data and detects water leaks, reporting sensor readings to the main vehicle controller while the ROV is submerged.

<img width="1239" height="417" alt="image" src="https://github.com/user-attachments/assets/65e71aa2-9981-436b-920a-9c6b62fb8b94" />

## Overview

| | |
|---|---|
| **Design tool** | Altium Designer |
| **Board type** | Sensor interface / monitoring board |
| **Deployment** | Internal, McMaster Underwater Robotics Team ROV |
| **License (hardware)** | CERN-OHL-W v2 |
| **Status** | *in testing)* |

## Features

- **Real-time environmental monitoring** — continuous temperature readings via 1-Wire, streamed to the main controller during dive operations
- **Early leak detection** — custom BJT-based sensing circuit flags water ingress before it reaches critical electronics, acting as a hull-integrity failsafe
- **6-axis motion/orientation sensing** — onboard IMU provides accelerometer and gyro data for vehicle state estimation
- **Single-connector vehicle integration** — compact JST GH interconnect for clean, low-profile wiring inside the enclosure
- **Designed for sealed enclosure operation** — components and layout chosen for use inside a submerged, sealed electronics housing

## Functionality

This board is responsible for gathering environmental and structural health data from within the ROV enclosure and passing it to the main controller:

- **Temperature sensing** — [DS18B20Z](https://www.analog.com/en/products/ds18b20.html) digital temperature sensor (1-Wire interface)
- **Leak detection** — Custom BJT-based leakage sensor circuit to detect water ingress inside the hull before it reaches critical electronics
- **Orientation / motion tracking** — [MPU-6050](https://invensense.tdk.com/products/motion-tracking/6-axis/mpu-6050/) 6-axis IMU (3-axis accelerometer + 3-axis gyroscope)
- **Vehicle interconnect** — [BM02B-GHS-TBT(LF)(SN)](https://www.jst-mfg.com/) JST connector, used to link this board to the rest of the vehicle's electrical system

The board is designed to sit inside the sealed electronics housing and continuously report sensor data, with the leak detection circuit acting as an early-warning system for hull integrity.


<img width="1244" height="425" alt="image" src="https://github.com/user-attachments/assets/cefd6664-7161-4572-9068-233e9b037b77" />

## Sensors & Key Components

| Component | Function | Interface |
|---|---|---|
| DS18B20Z | Digital temperature sensing | 1-Wire |
| BJT-based leak sensor (custom) | Water ingress / leak detection | Analog / GPIO |
| MPU-6050 | 6-axis IMU (accel + gyro) | I²C |
| BM02B-GHS-TBT(LF)(SN) | Board-to-vehicle interconnect | JST GH, 2-pin |

<img width="1190" height="768" alt="image" src="https://github.com/user-attachments/assets/b8e584b7-3d3d-4386-8295-04eef9640715" />

## Getting Started

### Opening the project
1. Install [Altium Designer](https://www.altium.com/altium-designer).
2. Open `Hardware/Project/*.PrjPcb`.
3. Schematic and PCB layout will load from the `Schematic/` and `PCB/` subfolders.

### Manufacturing
Gerbers, drill files, BOM, and pick-and-place files for ordering/assembly are in the `Manufacturing/` folder. See `Manufacturing/BOM/` for the parts list before ordering.

## License

Hardware design files (schematics, PCB layout, Gerbers, BOM) in this repository are licensed under the **CERN Open Hardware Licence Version 2 - Weakly Reciprocal (CERN-OHL-W v2)**. See [LICENSE](LICENSE) for full terms.

Any accompanying firmware/software, if added to this repository, will be licensed separately (e.g. MIT) and noted in its own subfolder.

## Team

Developed by **Omer Khalil** for the [**McMaster Underwater Robotics Team (MURT)**](https://www.macmurt.com/).
