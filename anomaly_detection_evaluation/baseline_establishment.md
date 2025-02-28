# Baseline Establishment

## Importance of Baseline
A baseline is the foundation for evaluating anomaly detection (AD) techniques, representing the normal behavior of smart home devices across various scenarios. Establishing a robust baseline ensures that deviations from expected patterns are accurately identified as anomalies. This process is critical for minimizing false positives and improving the reliability of AD models.

---

## Steps for Baseline Establishment

### 1. Scenario Coverage
To create a comprehensive baseline, capture data that reflects the full spectrum of device states and interactions. 

#### Device States
For each device, capture data under:
- **State Variations**:
  - Example: Low, medium, and high fan speeds for a Xiaomi air purifier.
- **Idle and Active States**:
  - Include periods of inactivity and normal operation to provide a complete picture of device behavior.

#### Interaction Types
- **Self-Initiated Actions**:
  - Actions performed autonomously by the device (e.g., a motion sensor triggering a light).
- **Controller-Initiated Actions**:
  - Actions triggered by external controllers like Home Assistant.
- **App-Initiated Actions**:
  - Actions performed via the device's smartphone application.

---

### 2. Multi-Controller Data
To ensure comprehensive baseline data, capture actions performed through different control methods:

- **Local Control**:
  - Interact directly with the device's physical buttons or controls.
- **Home Assistant (HA) Control**:
  - Use Home Assistant to perform the same action executed locally.
- **App Control**:
  - Use the device's associated app to replicate the same action.

This approach ensures consistency across control methods and identifies any discrepancies in device responses based on the controller.

---

### 3. Data Capture Setup
A reliable data capture setup is essential for accurately recording baseline behavior. Follow these steps to configure the environment:

- **Network Monitoring Tools**:
  - **[Wireshark](https://www.wireshark.org/)**: Analyze network traffic in detail.
  - **[TCPDump](https://www.tcpdump.org/)**: Capture raw network traffic for in-depth analysis.

- **Data Storage**:
  - Use a time-series database such as **[InfluxDB](https://hub.docker.com/_/influxdb)** to store and analyze captured data.

#### Example TCPDump Command
The following command captures network traffic and saves it to a `.pcap` file for later analysis:
```bash
sudo tcpdump -i any -w baseline_capture.pcap
```
- Ensure that the captured data reflects the baseline by monitoring traffic during regular device operation.
---
## Key Benefits

- **Comprehensive Baseline**: Ensures all device states and interactions are accounted for.
- **Data Consistency**: Capturing actions through multiple controllers minimizes discrepancies.
- **Efficient Analysis**: Storing data in a time-series database facilitates detailed and long-term analysis.

---

## Additional Resourcesbaseline_establishment.md

To assist in establishing and analyzing baselines, refer to the following resources:

- [Wireshark Official Guide](https://www.wireshark.org/docs/)
- [InfluxDB Docker Hub](https://hub.docker.com/_/influxdb)
- [TCPDump Documentation](https://www.tcpdump.org/manpages/)


---

## Acknowledgments
This guide is based on extensive research and real-world implementations in anomaly detection for IoT environments. Special thanks to the contributors who developed the detailed methodologies that ensure robust and reliable baselines for AD evaluations.
