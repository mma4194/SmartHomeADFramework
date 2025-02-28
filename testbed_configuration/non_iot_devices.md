# Non-IoT Devices

## Overview
Non-IoT devices are pivotal in the smart home testbed, enabling control, data management, and network traffic capture. These devices work in tandem with IoT components to create a complete, functional environment for evaluating anomaly detection (AD) techniques.

---

## Raspberry Pi
Raspberry Pi devices are versatile, cost-effective tools that power essential functions of the testbed. Each Raspberry Pi is configured to host critical software and manage specific aspects of the testbed's operation.

- **Purpose**:
  - Hosts Home Assistant to control and automate IoT devices.
  - Provides lightweight data processing and real-time visualization for monitoring and analysis.

- **Operating Systems**:
  - **Raspberry Pi 1**: 
    - Runs Home Assistant OS, serving as the centralized platform for device control and automation.
    - Ensures seamless integration with Zigbee, Z-wave, and Wi-Fi devices.
  - **Raspberry Pi 2**: 
    - Runs **DietPi**, a lightweight OS optimized for minimal resource usage.
    - Hosts tools like Grafana and InfluxDB for efficient data processing and visualization.

- **Use Cases**:
  - Facilitates anomaly detection by providing a streamlined interface for data collection and automation.
  - Offers remote access capabilities for monitoring and managing the testbed.

---

## Router
The router is a critical component, functioning as the central hub for network traffic and device connectivity. Its advanced configurations support traffic capture and detailed analysis.

- **Model**: Linksys WRT3200 ACM
- **Firmware**: OpenWRT
  - **Features**:
    - Configured with TCPDump to capture all network traffic, including Wi-Fi and Ethernet data.
    - Supports dual-boot functionality, enabling easy switching between OpenWRT and the router’s default firmware.
  - **Use Case**:
    - Provides comprehensive network traffic logs for anomaly detection research.
    - Ensures robust network connectivity and facilitates real-time analysis of traffic patterns.

---

## Key Features
- **Scalability**: Raspberry Pi devices are easily configurable and scalable for additional functions.
- **Network Monitoring**: OpenWRT-enabled router provides granular control over network data capture.
- **Data Integration**: Seamless integration of non-IoT devices with IoT components for unified anomaly detection workflows.

---

## Additional Resources
To set up and configure the non-IoT devices, explore the following resources:
- [DietPi Installation Guide](https://dietpi.com/docs/install/)
- [Home Assistant Documentation](https://www.home-assistant.io/)
- [OpenWRT Configuration](https://openwrt.org/docs/guide-quick-start/start)

---

## Acknowledgments
The non-IoT devices listed here form the backbone of the smart home testbed, ensuring efficient operation and data management. Special thanks to the developers and manufacturers for their innovative and versatile solutions that enable advanced anomaly detection research.
