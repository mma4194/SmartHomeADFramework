# BLE Anomalies Repository

## Introduction
This section explores BLE (Bluetooth Low Energy) anomalies, their implementation, and detection. The focus is to provide an accessible guide for students and researchers to understand and simulate these anomalies in controlled environments. 

## Overview
BLE anomalies can compromise device communication, privacy, and system functionality. This repository details three key BLE anomalies:

1. Reconnaissance.
2. Spam.
3. Jamming.

Each anomaly includes an explanation, implementation steps, and its system/user impacts.

## Getting Started
### Prerequisites
Ensure you have the following hardware and software:

- **Hardware**:
  - Laptop with a Bluetooth adapter that supports BLE.
  - Flipper Zero for BLE spamming.
  - Open Sniffer device for jamming.
- **Software**:
  - Bettercap (for reconnaissance).
  - Xtreme firmware for Flipper Zero.

### Setting Up the Environment
1. **Install Required Tools**:
   - Update system packages:
     ```bash
     sudo apt update && sudo apt upgrade -y
     ```
   - Install Bettercap:
     ```bash
     sudo apt install bettercap
     ```
2. **Set Up Jamming Hardware**:
   - Connect the Open Sniffer to your laptop as outlined below.

### Disclaimer
This repository is intended for educational and research purposes only. Unauthorized use of these techniques may violate laws and regulations. Ensure you have explicit permission before testing on any BLE devices or networks.

## Anomalies Explained

### 1. BLE Reconnaissance
#### What is it?
This technique scans for nearby BLE devices and gathers information about their characteristics and activity.

#### Tools and Hardware
- **Hardware**: Laptop with Bluetooth adapter.
- **Software**: Bettercap.

#### How to Implement
1. Install Bettercap:
   ```bash
   sudo apt install bettercap
   ```
2. Execute the following command to start BLE reconnaissance:
   ```bash
   sudo bettercap -eval "ble.recon on"
   ```
3. Observe the output for BLE device details.

#### Detection Features
- Increased BLE advertising packets in traffic logs.

#### Real-World Impact
- **System**: No direct impact.
- **User**: Privacy concerns due to unauthorized data gathering.

---

### 2. BLE Spam Attack

#### What is it?
A BLE spam attack involves flooding nearby BLE devices with excessive connection requests or advertising packets, disrupting normal operation and connectivity. This anomaly, illustrated by targeting devices such as iPhones, is particularly difficult to detect due to its random MAC address changes, making it appear as if the packets originate from multiple sources. 

Using a Flipper Zero device equipped with Xtreme firmware enables the execution of a comprehensive range of BLE spam attacks, including BLE spoofing designed to impersonate legitimate smart devices like Samsung smartwatches and earbuds to perform malicious acts.

#### Tools and Hardware
- **Hardware**: Flipper Zero.
- **Software**: Xtreme BLE Spam.

#### How to Implement
1. Run `kitchen sink` BLE spam mode on Flipper Zero.

#### Detection Features
- Increased number of unsolicited BLE connection requests.
- Frequent unexpected disconnections in BLE devices.
- High volume of BLE advertising packets in traffic logs.

#### Real-World Impact
- **System**: Device communication failures.
- **User**: Connectivity disruptions, degraded user experience, potential device crashes.

---

### 3. BLE Jamming
#### What is it?
Disrupts BLE communication by interfering with specific BLE channels, causing device unresponsiveness.

#### Tools and Hardware
- **Hardware**: Open Sniffer device.

#### How to Implement
1. Connect the Open Sniffer to your laptop using Ethernet and power cables.
2. Configure the host IP address:
   - IP: `10.10.10.1`
   - Mask: `255.255.255.0`
3. Open a browser and navigate to:
   ```bash
   http://10.10.10.2
   ```
4. Access the Continuous Transmission (CT) page and set the following:
   - **Channel**: Select BLE broadcasting channels (37, 38, or 39 corresponding to 2.402, 2.426, or 2.480 GHz).
   - **Mode**: `PRBS: 0xAAAA`
   - **Modulation**: `Modulation O-QPSK_250`
   - **Power Level**: `3.0`
5. Click the "Launch" button to start the jamming operation.

#### Detection Features
- Significant packet loss and drop in incoming BLE packets.

#### Real-World Impact
- **System**: Prevents normal actuation and operation of BLE devices.
- **User**: Loss of control and inconvenience.

## Detection Techniques
- Use BLE traffic monitoring tools to detect anomalies in advertising packet rates or packet loss.
- Analyze logs with tools like Wireshark to identify traffic patterns.

## Additional Resources
- [Bettercap Documentation](https://www.bettercap.org/)
- [Open Sniffer Guidelines](https://www.sewio.net/open-sniffer/)
- [Flipper Zero](https://flipperzero.one/)
- [Xtreme firmware for Flipper Zero](https://github.com/Flipper-XFW/Xtreme-Firmware)

## Acknowledgments
This content is adapted from research on BLE anomaly detection in smart environments. The authors acknowledge the importance of ethical practices in implementing and testing these techniques.
