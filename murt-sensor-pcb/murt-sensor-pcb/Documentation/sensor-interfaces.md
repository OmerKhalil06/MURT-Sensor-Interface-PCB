# Sensor & Connector Reference

Quick reference for the sensors and connector used on this board. Fill in the exact pin/net names once the schematic is finalized.

## DS18B20Z — Temperature Sensor
- **Interface:** 1-Wire
- **Package:** SOP-8 (Z suffix variant)
- **Datasheet:** https://www.analog.com/en/products/ds18b20.html
- **Notes:** Requires a pull-up resistor on the data line (typically 4.7 kΩ). Confirm parasite-power vs. external-power mode used in this design.

## Custom BJT Leak Sensor
- **Function:** Detects water ingress inside the enclosure by sensing conductivity/current change across exposed contacts when water bridges them.
- **Topology:** *(Document the BJT configuration — e.g., common-emitter switch triggering a GPIO interrupt on the main controller.)*
- **Notes:** *(Add trip threshold, response time, and any calibration notes here.)*

## MPU-6050 — 6-Axis IMU
- **Interface:** I²C
- **Outputs:** 3-axis accelerometer, 3-axis gyroscope
- **Datasheet:** https://invensense.tdk.com/products/motion-tracking/6-axis/mpu-6050/
- **Notes:** Confirm I²C address (AD0 pin strapping) and pull-up resistor values used on SDA/SCL.

## BM02B-GHS-TBT(LF)(SN) — Vehicle Interconnect
- **Type:** JST GH series, 2-position, top entry, with friction lock
- **Function:** Connects this sensor board to the rest of the vehicle's wiring harness (power + data, or similar — confirm pinout).
- **Datasheet:** https://www.jst-mfg.com/
- **Mating connector:** *(Add mating housing/crimp part numbers here.)*

## Board-Level Notes
*(Add supply voltage, current draw, connector pinout table, and any protocol/timing details the main controller firmware needs to know.)*
