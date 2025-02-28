# Testbed Configuration for Smart Home Testbed

## Introduction
This section outlines the setup and configuration of a smart home testbed designed for evaluating anomaly detection techniques. The configuration includes IoT devices, controllers, hubs, non-IoT devices, and software tools, ensuring a realistic and versatile test environment.

---

## 1. Testbed Configuration
The repository includes detailed documentation for setting up and configuring the smart home testbed:

- **[Testbed Overview](testbed_overview.md)**:
  - General architecture and components of the testbed.
- **[IoT Devices](iot_devices.md)**:
  - List and configuration of IoT devices in the testbed.
- **[Controllers and Hubs](controllers_and_hubs.md)**:
  - Details of controllers and hubs used to manage IoT devices.
- **[Non-IoT Devices](non_iot_devices.md)**:
  - Supporting devices like laptops, routers, and sniffers.
- **[Software Tools](software_tools.md)**:
  - Tools and software used for network monitoring, data capture, and anomaly detection.

---

## 2. Common Pitfalls and Recommendations

| Pitfall                        | Recommendation                                              |
|--------------------------------|-------------------------------------------------------------|
| **Hub feature limitations**    | Use hubs capable of capturing and managing all IoT features.|
| **Database choice mismatch**   | Employ a time-series database like InfluxDB for better performance.|
| **Non-COTS sensor usage**      | Ensure all sensors are Commercial Off-The-Shelf (COTS) for reliability.|
| **Ecosystem limitations**      | Deploy a smart home ecosystem that supports all required functionalities.|

---

## Additional Resources

- [InfluxDB Setup](https://hub.docker.com/_/influxdb)
- [Grafana Visualization](https://grafana.com/docs/)

---

## Acknowledgments
This configuration guide is based on extensive research and practical applications in IoT environments. Special thanks to the contributors for their expertise and recommendations for building robust smart home testbeds.
