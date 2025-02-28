# Software Tools

## Overview
The smart home testbed leverages a suite of software tools to manage devices, process data, and monitor network traffic. These tools are carefully chosen to ensure efficient operation, scalability, and detailed analysis for anomaly detection (AD) evaluations.

---

## Operating Systems
Operating systems in the testbed are optimized for specific roles, enabling seamless device management and data capture:

- **[DietPi](https://dietpi.com/)**:
  - A lightweight OS ideal for resource-constrained environments like Raspberry Pi.
  - **Use Case**: Hosts data processing tools such as Grafana and InfluxDB.

- **[Home Assistant OS](https://www.home-assistant.io/)**:
  - A purpose-built OS for smart home automation and control.
  - **Use Case**: Centralizes control and integrates Zigbee, Z-wave, and Wi-Fi devices.

- **[OpenWRT](https://openwrt.org/)**:
  - A customizable router OS that enables advanced network configurations.
  - **Use Case**: Captures network traffic for detailed analysis using tools like TCPDump.

---

## Docker Containers
Docker containers streamline the deployment and management of services in the testbed. Key containers include:

- **[Grafana](https://grafana.com/docs/grafana/latest/setup-grafana/installation/docker/)**:
  - A powerful visualization tool for time-series data.
  - **Use Case**: Real-time monitoring of IoT metrics and network traffic.

- **[InfluxDB](https://hub.docker.com/_/influxdb)**:
  - A time-series database optimized for IoT and network data storage.
  - **Use Case**: Stores metrics for visualization and anomaly detection.

- **[Portainer](https://docs.portainer.io/start/install-ce/server/docker)**:
  - A user-friendly GUI for managing Docker containers.
  - **Use Case**: Simplifies container deployment and maintenance.

- **[Telegraf](https://hub.docker.com/_/telegraf)**:
  - A system metrics collector for CPU, memory, and disk usage.
  - **Use Case**: Enhances performance monitoring of testbed devices.

- **[Flame Dashboard](https://hub.docker.com/r/pawelmalak/flame)**:
  - A centralized dashboard for accessing testbed services.
  - **Use Case**: Organizes and simplifies navigation across Docker-hosted applications.

- **[Snippet Box](https://hub.docker.com/r/pawelmalak/snippet-box)**:
  - A self-hosted tool for organizing reusable code snippets.
  - **Use Case**: Stores frequently used scripts and commands for testbed operations.

---

## Network Tools
Network analysis is a cornerstone of the testbed, facilitated by powerful tools for traffic capture and anomaly detection:

- **[TCPDump](https://www.tcpdump.org/)**:
  - A lightweight command-line tool for capturing network traffic.
  - **Use Case**: Collects detailed network logs directly from the router for AD analysis.

- **[Wireshark](https://www.wireshark.org/)**:
  - An advanced packet analyzer for identifying patterns and anomalies in traffic.
  - **Use Case**: Provides granular insights into network behavior and potential anomalies.

- **[ZeroTier](https://www.zerotier.com/)**:
  - A secure VPN solution for remote access to the testbed.
  - **Use Case**: Enables off-site monitoring and management of testbed components.

---

## Key Features
- **Efficiency**: Lightweight OS and Docker containers ensure optimal resource utilization.
- **Scalability**: Modular setup allows easy expansion of testbed capabilities.
- **Comprehensive Monitoring**: Integration of network tools and visualization platforms enhances anomaly detection workflows.

---

## Additional Resources
For installation and configuration guides, refer to:
- [DietPi Installation Guide](https://dietpi.com/docs/install/)
- [OpenWRT Setup](https://openwrt.org/docs/guide-quick-start/start)
- [Grafana Tutorials](https://grafana.com/tutorials/)

---

## Acknowledgments
The software tools employed in this testbed are integral to its functionality and efficiency. Special thanks to the contributors and developers of these tools for their continuous innovation and support in advancing IoT research.
