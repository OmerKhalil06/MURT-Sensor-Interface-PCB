# MURT Sensor Interface & Monitoring PCB

Sensor interface and monitoring board for the **McMaster Underwater Robotics Team (MURT)** ROV/submarine platform. This board collects environmental and vehicle-state data and detects water leaks, reporting sensor readings to the main vehicle controller while the ROV is submerged.

![PCB Render](Images/pcb-render.png)
*Add a top-down render or photo of the assembled board here.*

## Overview

| | |
|---|---|
| **Design tool** | Altium Designer |
| **Board type** | Sensor interface / monitoring board |
| **Deployment** | Internal, McMaster Underwater Robotics Team ROV |
| **License (hardware)** | CERN-OHL-W v2 |
| **Status** | *(e.g. Rev A — in testing)* |

## Functionality

This board is responsible for gathering environmental and structural health data from within the ROV enclosure and passing it to the main controller:

- **Temperature sensing** — [DS18B20Z](https://www.analog.com/en/products/ds18b20.html) digital temperature sensor (1-Wire interface)
- **Leak detection** — Custom BJT-based leakage sensor circuit to detect water ingress inside the hull before it reaches critical electronics
- **Orientation / motion tracking** — [MPU-6050](https://invensense.tdk.com/products/motion-tracking/6-axis/mpu-6050/) 6-axis IMU (3-axis accelerometer + 3-axis gyroscope)
- **Vehicle interconnect** — [BM02B-GHS-TBT(LF)(SN)](https://www.jst-mfg.com/) JST connector, used to link this board to the rest of the vehicle's electrical system

The board is designed to sit inside the sealed electronics housing and continuously report sensor data, with the leak detection circuit acting as an early-warning system for hull integrity.

## Repository Structure

```
murt-sensor-pcb/
├── Hardware/
│   ├── Project/       # Altium project file (.PrjPcb) and workspace
│   ├── Schematic/      # Schematic files (.SchDoc)
│   └── PCB/            # PCB layout files (.PcbDoc)
├── Manufacturing/
│   ├── Gerbers/        # Gerber files for fabrication
│   ├── Drill/          # Drill files (NC drill / Excellon)
│   ├── BOM/            # Bill of materials
│   └── PickAndPlace/   # Centroid / pick-and-place files for assembly
├── Documentation/       # Datasheets, design notes, pinout references
└── Images/              # Renders, photos, schematic screenshots
```

## Sensors & Key Components

| Component | Function | Interface |
|---|---|---|
| DS18B20Z | Digital temperature sensing | 1-Wire |
| BJT-based leak sensor (custom) | Water ingress / leak detection | Analog / GPIO |
| MPU-6050 | 6-axis IMU (accel + gyro) | I²C |
| BM02B-GHS-TBT(LF)(SN) | Board-to-vehicle interconnect | JST GH, 2-pin |

*(Update pin counts, connector counts, and interface details as needed to match your final schematic.)*

## Getting Started

### Opening the project
1. Install [Altium Designer](https://www.altium.com/altium-designer).
2. Open `Hardware/Project/*.PrjPcb`.
3. Schematic and PCB layout will load from the `Schematic/` and `PCB/` subfolders.

### Manufacturing
Gerbers, drill files, BOM, and pick-and-place files for ordering/assembly are in the `Manufacturing/` folder. See `Manufacturing/BOM/` for the parts list before ordering.

## Revision History

| Rev | Date | Notes |
|---|---|---|
| A | *(date)* | Initial release |

## License

Hardware design files (schematics, PCB layout, Gerbers, BOM) in this repository are licensed under the **CERN Open Hardware Licence Version 2 - Weakly Reciprocal (CERN-OHL-W v2)**. See [LICENSE](LICENSE) for full terms.

Any accompanying firmware/software, if added to this repository, will be licensed separately (e.g. MIT) and noted in its own subfolder.

## Team

Developed by **[Your Name]** for the **McMaster Underwater Robotics Team (MURT)**.
*(Add link to team website/organization page here.)*
