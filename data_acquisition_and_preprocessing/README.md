# Data Acquisition and Preprocessing for Smart Home Testbed

## Introduction
This section describes the methods, tools, and scripts used to acquire and preprocess data from the smart home testbed, focusing on Wi-Fi, Zigbee, Z-wave, and BLE communication protocols. The goal is to ensure high-quality, realistic data capture to support the evaluation of anomaly detection techniques in IoT environments.

## 1. Data Acquisition

### Hardware Details
The following hardware components are used for data acquisition across different protocols:

- **Wi-Fi:** OpenWRT-compatible router (e.g., Linksys WRT3200 ACM) with OpenWRT firmware and TCPDump.
- **Zigbee:** CC2531 USB stick with SmartRF firmware.
- **Z-wave:** ACC-UZB3 stick with ZM5304 firmware.
- **BLE:** LAUNCHXL CC26X2R1 board using Sniffle firmware.

### Protocol-Specific Instructions

#### Wi-Fi
- **Hardware Requirements**: OpenWRT-compatible routers (e.g., Linksys WRT3200 ACM).
- **Software Tools**: OpenWRT OS, TCPDump.

**Steps to Capture Wi-Fi Traffic**:
1. **Installing OpenWRT**:
   - Download firmware from the [OpenWRT website](https://openwrt.org/).
   - Access the router’s admin interface to upload the firmware and reboot.
2. **Installing TCPDump**:
   - Connect to the router via SSH and run:
     ```bash
     opkg update
     opkg install tcpdump
     ```
3. **Mounting USB Storage**:
   - Insert a USB drive into the router and install USB utilities:
     ```bash
     opkg install kmod-usb-storage block-mount kmod-fs-ext4 kmod-fs-vfat
     ```
   - Mount the USB drive:
     ```bash
     mkdir -p /mnt/usb
     mount /dev/sda1 /mnt/usb
     ```
4. **Capturing Traffic**:
   - Use TCPDump to capture traffic and save it to the USB drive:
     ```bash
     tcpdump -i any -w /mnt/usb/capture.pcap
     ```
5. **Uploading Captures**:
   - Use RClone to upload data to cloud storage:
     ```bash
     rclone copy /mnt/usb/capture.pcap remote_name:/path/to/folder
     ```

#### Zigbee
- **Hardware Requirements**: CC2531 USB stick.
- **Software Tools**: SmartRF firmware, Wireshark.

**Steps to Capture Zigbee Traffic**:
1. Flash the CC2531 USB stick with SmartRF firmware ([instructions](https://www.zigbee2mqtt.io/advanced/zigbee/04_sniff_zigbee_traffic.html)).
2. Start capturing traffic with Wireshark:
   ```bash
   sudo whsniff -c 11 | wireshark -k -i -
   ```

#### Z-wave
- **Hardware Requirements**: ACC-UZB3 USB stick.
- **Software Tools**: Z-Wave Programmer, Z-Wave Zniffer.

**Steps to Capture Z-wave Traffic**:
1. Flash the ACC-UZB3 stick with Z-Wave Programmer.
2. Start capturing traffic using the [Z-Wave Zniffer User Guide](https://www.silabs.com/documents/public/user-guides/INS10249-Z-Wave-Zniffer-User-Guide.pdf).

#### BLE
- **Hardware Requirements**: LAUNCHXL CC26X2R1.
- **Software Tools**: Sniffle.

**Steps to Capture BLE Traffic**:
1. Install Sniffle from [GitHub](https://github.com/nccgroup/Sniffle).
2. Configure the device for multi-channel capture.
3. Capture traffic with specific BLE parameters.

---

## 2. Preprocessing

### Feature Extraction
- **Network Features**:
  - Packet size, flow duration, packet inter-arrival time.
- **Statistical Features**:
  - Mean, standard deviation, and median of packet lengths.
- **Tools**:
  - [Wireshark](https://www.wireshark.org/), [CICFlowMeter](https://github.com/hieulw/cicflowmeter).

**Steps to Preprocess Data**:
1. Load capture files into Wireshark.
2. Export features as CSV using custom scripts.
3. Use CICFlowMeter to calculate advanced metrics.

### Database Integration
- Use [InfluxDB](https://hub.docker.com/_/influxdb) to store time-series data.
- Connect InfluxDB with [Grafana](https://grafana.com/docs/grafana/latest/setup-grafana/installation/docker/) for visualization.

---

## 3. Common Pitfalls and Recommendations

| Pitfall                           | Recommendation                                              |
|-----------------------------------|-------------------------------------------------------------|
| Outdated sniffing hardware        | Ensure hardware supports the latest protocol versions.      |
| Port mirroring impact             | Capture traffic from the router and over-the-air instead.   |
| Zigbee encrypted traffic sniffing | Add the encryption key for Zigbee captured traffic.         |
| Missing over-the-air traffic      | Use dedicated sniffers for wireless traffic capture.        |
| Feature integration lacking       | Extract network features along with statistical ones.       |
| Basic data capture                | Go beyond IP addresses and port numbers.                   |
| Dynamic IP reliance               | Use MAC addresses as unique identifiers.                   |
| Inadequate storage solutions      | Use external storage or cloud integration for large datasets.|

---

## Additional Resources
- [Wireshark Tutorial](https://www.wireshark.org/)
- [Open Sniffer Guidelines](https://www.sewio.net/open-sniffer/)
- [Z-wave Zniffer Guide](https://www.silabs.com/documents/public/user-guides/INS10249-Z-Wave-Zniffer-User-Guide.pdf)

## Acknowledgments
This content is based on research into anomaly detection in IoT environments. The authors emphasize ethical and responsible practices in data acquisition and preprocessing.
