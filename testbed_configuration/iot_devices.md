# IoT Devices

## Overview
The IoT devices integrated into this testbed were strategically selected to mirror real-world smart home environments. These devices operate on diverse communication protocols, enabling a thorough evaluation of anomaly detection (AD) techniques. Their capabilities provide a robust platform for replicating common smart home scenarios and potential vulnerabilities.

---

## Devices

### 1. Wi-Fi Devices
Wi-Fi-enabled devices are integral to smart homes, offering high bandwidth and seamless compatibility across ecosystems. The testbed includes:

- **LiFx Smart Light Bulb**:
  - **Features**: Provides data on color settings, on/off state, and Received Signal Strength Indicator (RSSI), a critical metric for network-based anomaly detection.
  - **Use Case**: Lighting automation and network monitoring, particularly useful in detecting spoofing and jamming anomalies.
- **Xiaomi Air Purifier**:
  - **Features**: Equipped with sensors for air quality (PM2.5), temperature, and humidity, offering a comprehensive environmental profile.
  - **Use Case**: Environmental monitoring and anomaly profiling through sensor data analysis.
- **Reolink E1 Pro Camera**:
  - **Features**: Supports Real-Time Streaming Protocol (RTSP) for live video feeds, aiding in real-time surveillance and anomaly tracking.
  - **Use Case**: Security monitoring and advanced video-based anomaly detection.

---

### 2. Zigbee Devices
Zigbee devices are designed for energy efficiency and reliable mesh networking, making them ideal for smart homes. The testbed features:

- **Philips Hue Smart Bulbs**:
  - **Features**: Multi-color lighting options with programmable scenes.
  - **Connectivity**: Integrated through a Zigbee gateway for seamless operation.
  - **Use Case**: Smart lighting control and automation scenarios.
- **Aqara Motion Sensors**:
  - **Features**: Detect motion and vibrations, offering multi-faceted intrusion detection capabilities.
  - **Use Case**: Security systems and automation triggers (e.g., turning on lights upon motion detection).
- **Aqara Water Leak Sensors**:
  - **Features**: Detect water leaks, alerting users to potential maintenance issues.
  - **Use Case**: Preventative maintenance and early warning for water damage risks.

---

### 3. Z-wave Devices
Z-wave devices emphasize secure communication and broad compatibility, making them a cornerstone for smart home ecosystems. Included devices are:

- **Fibaro Motion Detector**:
  - **Features**: Monitors motion and temperature, providing dual-purpose functionality for security and environmental assessments.
  - **Use Case**: Real-time security monitoring and ambient condition analysis.
- **Fibaro CO Sensor**:
  - **Features**: Detects carbon monoxide levels and provides temperature data, ensuring safety in domestic environments.
  - **Use Case**: Hazard prevention and cross-validation with other environmental sensors for anomaly detection.

---

## Key Features
The combination of these devices ensures:
- **Protocol Diversity**: Integration of Wi-Fi, Zigbee, and Z-wave communication protocols for comprehensive testing.
- **Real-World Applicability**: Devices selected reflect common smart home setups to ensure realistic anomaly simulations.
- **Multi-Layered Data**: Devices provide data across network, environmental, and operational layers for robust anomaly detection analysis.

---

## Additional Resources
Explore the following documentation and APIs for device integration and control:
- [LiFx Smart Bulb API](https://api.developer.lifx.com/)
- [Philips Hue Developer Documentation](https://developers.meethue.com/)
- [Fibaro System Overview](https://www.fibaro.com/en/)

---

## Acknowledgments
The IoT devices included in this testbed were selected for their innovation, reliability, and relevance to smart home ecosystems. Special thanks to the device manufacturers for their comprehensive documentation and continued support in advancing IoT technology.
