# Testbed Overview

## Purpose
The smart home testbed is meticulously designed to simulate real-world conditions for evaluating anomaly detection (AD) techniques. By incorporating diverse communication protocols, IoT devices, and automation systems, it offers a robust framework for testing AD methods across various scenarios. This testbed emphasizes reliability, scalability, and comprehensive data collection to enhance the evaluation process.

---

## Components

The testbed consists of four primary components, each playing a critical role in replicating a realistic smart home environment:

### 1. IoT Devices
A variety of IoT devices have been integrated into the testbed to reflect the diversity of real-world smart homes:
- **Smart Lights**: Includes Philips Hue bulbs and light strips for automated lighting control.
- **Air Purifiers**: Monitors and improves air quality with detailed sensor readings.
- **Cameras**: Provides video feeds and supports protocols like RTSP for monitoring and anomaly profiling.
- **Sensors**: Includes motion, vibration, temperature, and water leak sensors for environment monitoring.
- **Smart Switches and Plugs**: Enhances device control and energy monitoring.

### 2. Controllers and Hubs
Controllers and hubs are critical for device management and protocol-specific communication:
- **Home Assistant**: A central automation system for managing all connected devices, enabling detailed logging and control.
- **Zigbee Gateways**: Such as the Conbee II dongle, facilitating communication for Zigbee-based devices.
- **Z-wave Hubs**: Includes Fibaro Home Center, ensuring seamless integration of Z-wave devices.

### 3. Non-IoT Devices
These devices provide infrastructure support for data capture, processing, and storage:
- **Raspberry Pi Units**: 
  - One unit runs Home Assistant OS to integrate and automate IoT devices.
  - The second unit runs data processing and visualization tools, including Grafana and InfluxDB.
- **OpenWRT-enabled Router**: 
  - Captures all network traffic using TCPDump for comprehensive data analysis.
  - Ensures robust network connectivity across all components.

### 4. Software Tools
Several software tools are deployed for monitoring, capturing, and analyzing network and device data:
- **TCPDump**: Captures raw network traffic for analysis.
- **InfluxDB**: A lightweight time-series database for efficient storage of network metrics and device logs.
- **Grafana**: Provides detailed visualization of data trends and real-time monitoring.
- **Additional Tools**:
  - **Wireshark**: Analyzes packet-level network data for anomaly detection.
  - **Bettercap**: A versatile tool for network reconnaissance and testing.
  - **RClone**: Automates data backups to cloud storage solutions.

---

## Protocols Supported

The testbed supports multiple communication protocols to accommodate the diverse needs of smart home environments:
- **Wi-Fi**: Provides high-bandwidth communication for devices like cameras, smart TVs, and some sensors.
- **Zigbee**: Ideal for low-power devices such as smart lights, motion sensors, and switches.
- **Z-wave**: Ensures secure and reliable communication with IoT devices like thermostats and smart hubs.
- **BLE (Bluetooth Low Energy)**: Supports low-energy, short-range communication for wearables and smart locks.

This multi-protocol support allows comprehensive testing of AD techniques under varied conditions and use cases.

---

## Additional Resources

Explore the following resources to set up and optimize your testbed environment:

- [Home Assistant Setup](https://www.home-assistant.io/installation/): Guides on installing and configuring Home Assistant.
- [OpenWRT Firmware](https://openwrt.org/): Instructions for installing and customizing OpenWRT on routers.
- [Grafana Tutorials](https://grafana.com/tutorials/): Learn to visualize and analyze data effectively using Grafana.

---

## Acknowledgments

This overview is inspired by extensive research aimed at advancing the development of robust testbeds for anomaly detection in IoT ecosystems. We extend our gratitude to all contributors for their technical insights and support in creating this comprehensive framework.
