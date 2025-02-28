# Controllers and Hubs

## Overview
Controllers and hubs are the backbone of the smart home testbed, enabling communication, control, and data management across diverse IoT devices and protocols. These components are crucial for creating a realistic and scalable environment for anomaly detection (AD) evaluation.

---

## Zigbee Gateways

- **Conbee II Dongle**:
  - **Features**: 
    - Supports a wide range of Zigbee devices, including those from different manufacturers.
    - Provides advanced data capture capabilities, making it ideal for monitoring device interactions.
    - Facilitates seamless integration with Home Assistant and other platforms.
  - **Use Case**: 
    - Acts as the primary gateway for all Zigbee-based devices, ensuring smooth communication.
    - Enables detailed logging and analysis of device behaviors for anomaly detection purposes.

---

## Z-wave Hubs

- **Fibaro Home Center**:
  - **Features**:
    - Serves as the central hub for Z-wave devices, supporting secure and efficient communication.
    - Offers robust automation capabilities tailored for Z-wave devices.
  - **Use Case**: 
    - Centralizes control for Z-wave-enabled devices in the testbed.
    - Ensures reliable data transmission for security and environmental monitoring applications.

---

## Home Automation Systems

- **Home Assistant (HA)**:
  - **Features**:
    - Open-source automation platform supporting Zigbee, Z-wave, and Wi-Fi protocols.
    - Provides a centralized interface for managing and automating IoT devices.
    - Offers extensive integrations and community-developed plugins for added functionality.
  - **Protocol Support**: 
    - Compatible with Zigbee, Z-wave, Wi-Fi, and other IoT standards.
  - **Use Case**:
    - Acts as the core automation system in the testbed, handling device control, automation rules, and logging.
    - Facilitates anomaly detection by enabling device-specific data capture and control.

---

## Voice Assistants

Voice assistants enhance the testbed’s usability by providing natural language interaction and additional control interfaces:

- **Google Home**:
  - **Features**:
    - Voice command support for controlling IoT devices.
    - Integration with Home Assistant for extended functionalities.
  - **Use Case**: 
    - Simplifies device interaction through voice commands, offering an accessible and intuitive control method.

- **Amazon Echo Studio and Echo Show 15**:
  - **Features**:
    - Combines voice control with visual displays for device monitoring and interaction.
    - Provides detailed feedback and multi-device control through Amazon Alexa.
  - **Use Case**: 
    - Enhances the smart home experience with voice and visual interfaces, supporting anomaly detection through better interaction and monitoring capabilities.

---

## Key Features

- **Protocol Diversity**: Supports Zigbee, Z-wave, and Wi-Fi communication for seamless integration.
- **Centralized Control**: Home Assistant serves as the unified platform for automation, logging, and monitoring.
- **Enhanced Usability**: Voice assistants and visual displays improve accessibility and interaction with devices.

---

## Additional Resources

To set up and configure the controllers and hubs in your testbed, refer to the following resources:
- [Conbee II Documentation](https://phoscon.de/en/conbee2)
- [Fibaro Home Center Guide](https://manuals.fibaro.com/home-center-3/)
- [Home Assistant Installation](https://www.home-assistant.io/installation/)

---

## Acknowledgments

The controllers and hubs listed here were chosen for their reliability and advanced features, ensuring a robust and realistic testbed environment. Special thanks to the developers and manufacturers for their contributions to the IoT ecosystem.
