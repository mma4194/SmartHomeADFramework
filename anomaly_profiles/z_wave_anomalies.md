# Z-wave Anomalies Repository

## Introduction
This section focuses on Z-wave anomalies, providing a detailed guide for simulating and understanding their impact on smart home networks. Z-wave is widely used in IoT devices, and its vulnerabilities can lead to disruptions in smart home environments.

## Overview
Z-wave anomalies disrupt communication and operation within Z-wave networks, potentially causing system failures and user inconvenience. This repository covers two critical Z-wave anomalies:

1. Jamming
2. Packet Injection (DoS)

Each anomaly includes an explanation, implementation steps, and detection strategies.

## Getting Started
### Prerequisites
Ensure you have the following hardware and software:

- **Hardware**:
  - Open Sniffer Gen3 device.
- **Software**:
  - None (operations are browser-based).

### Setting Up the Environment
1. **Hardware Setup**:
   - Connect the Open Sniffer to your laptop via Ethernet and power cable.
2. **Network Configuration**:
   - Set the host IP address to `10.10.10.1` and subnet mask to `255.255.255.0`.
   - Open a browser and navigate to `http://10.10.10.2`.

### Disclaimer
This repository is intended for educational and research purposes only. Unauthorized use of these techniques may violate laws and regulations. Ensure explicit permission before testing Z-wave devices or networks.

## Anomalies Explained

### 1. Z-wave Jamming
#### What is it?
Broadcasts signals to override legitimate Z-wave communications, leading to denial of service.

#### Tools and Hardware
- **Hardware**: Open Sniffer Gen3.

#### How to Implement
1. Connect the Open Sniffer to your laptop and configure the network settings.
2. Open a browser and navigate to `http://10.10.10.2`.
3. Access the Continuous Transmission (CT) page and set the following:
   - **Frequency**: Select the Z-wave frequency used by the target device (e.g., 868.42 MHz in Europe).
   - **Mode**: `PRBS: 0xAAAA`
   - **Modulation**: `Modulation O-QPSK_250`
   - **Power Level**: `3.0`
4. Click "Launch" to start jamming.

#### Detection Features
- Significant packet loss in Z-wave channels.

#### Real-World Impact
- **System**: Prevents actuation of Z-wave devices.
- **User**: Loss of control and inconvenience due to unresponsive devices.

---

### 2. Z-wave Packet Injection (DoS)
#### What is it?
Injects malicious packets to flood the Z-wave network, overwhelming it and causing devices to become unresponsive.

#### Tools and Hardware
- **Hardware**: Open Sniffer Gen3.

#### How to Implement
1. Connect the Open Sniffer to your laptop and configure the network settings.
2. Open a browser and navigate to `http://10.10.10.2`.
3. Access the Injection Mode page and set the following:
   - **Frequency**: Select the Z-wave frequency used by the target device.
   - **Modulation**: `Modulation O-QPSK_250`
   - **Power Level**: `3.0`
   - **Packet Configuration**:
     - Specify the number of packet repeats.
     - Define the time interval between packets (shorter intervals increase disruption likelihood).
     - Write the desired payload in the "Packet Payload" box.
4. Click "Launch" to start packet injection.

#### Detection Features
- Sudden spike in packet flow and transmission delays.

#### Real-World Impact
- **System**: Prevents actuation and operation of Z-wave devices.
- **User**: Loss of control and inconvenience due to system unresponsiveness.

## Detection Techniques
- Monitor Z-wave network traffic for anomalies such as packet loss (jamming) or surges in packet flow (DoS).
- Use tools like spectrum analyzers to detect radio interference during jamming events.

## Additional Resources
- [Open Sniffer Guidelines](https://www.sewio.net/open-sniffer/)
- [Z-wave Protocol Overview](https://z-wavealliance.org/)

## Acknowledgments
This content is adapted from research on Z-wave anomaly detection and IoT security. The authors emphasize the importance of ethical practices in implementing these techniques.
