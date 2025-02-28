# Zigbee Anomalies Repository

## Introduction
This section explores Zigbee anomalies, providing a detailed guide for simulating and understanding their impact on communication within Zigbee networks. It is aimed at researchers and students interested in IoT security and network anomaly detection.

## Overview
Zigbee anomalies disrupt the communication between IoT devices, leading to potential system failures and user inconvenience. This repository covers two key Zigbee anomalies:

1. Jamming
2. Packet Injection (DoS)

Each anomaly includes an explanation, implementation guide, and detection strategies.

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
This repository is intended for educational and research purposes only. Unauthorized use of these techniques may violate laws and regulations. Ensure explicit permission before testing Zigbee devices or networks.

## Anomalies Explained

### 1. Zigbee Jamming
#### What is it?
Zigbee jamming saturates the Zigbee frequency band with interfering radio signals, disrupting device communication.

#### Tools and Hardware
- **Hardware**: Open Sniffer Gen3.

#### How to Implement
1. Connect the Open Sniffer to your laptop and configure the network settings.
2. Open a browser and navigate to `http://10.10.10.2`.
3. Access the Continuous Transmission (CT) page and set the following:
   - **Frequency**: Select the Zigbee frequency used by the target device (commonly 2.4 GHz).
   - **Mode**: `PRBS: 0xAAAA`
   - **Modulation**: `Modulation O-QPSK_250`
   - **Power Level**: `3.0`
4. Click "Launch" to start jamming.

#### Detection Features
- Significant packet loss in Zigbee channels.

#### Real-World Impact
- **System**: Prevents actuation of Zigbee devices.
- **User**: Loss of control and inconvenience due to unresponsive devices.

---

### 2. Zigbee Packet Injection (DoS)
#### What is it?
Packet injection overwhelms the Zigbee network by transmitting arbitrary packets, causing devices to become unresponsive.

#### Tools and Hardware
- **Hardware**: Open Sniffer Gen3.

#### How to Implement
1. Connect the Open Sniffer to your laptop and configure the network settings.
2. Open a browser and navigate to `http://10.10.10.2`.
3. Access the Injection Mode page and set the following:
   - **Frequency**: Select the Zigbee frequency used by the target device.
   - **Modulation**: `Modulation O-QPSK_250`
   - **Power Level**: `3.0`
   - **Packet Configuration**:
     - Specify the number of packet repeats.
     - Define the time interval between packets (shorter intervals increase the likelihood of disruption).
     - Write the desired payload in the "Packet Payload" box.
4. Click "Launch" to start the packet injection.

#### Detection Features
- Sudden spike in packet flow within the Zigbee network.

#### Real-World Impact
- **System**: Prevents actuation and operation of Zigbee devices.
- **User**: Loss of control and inconvenience due to system unresponsiveness.

## Detection Techniques
- Monitor Zigbee network traffic for anomalies such as packet loss (jamming) or surges in packet flow (DoS).
- Use tools like spectrum analyzers to detect radio interference during jamming events.

## Additional Resources
- [Open Sniffer Guidelines](https://www.sewio.net/open-sniffer/)
- [Zigbee Protocol Overview](https://zigbeealliance.org/)

## Acknowledgments
This content is adapted from research on Zigbee anomaly detection and IoT security. The authors emphasize the importance of ethical practices in implementing these techniques.
