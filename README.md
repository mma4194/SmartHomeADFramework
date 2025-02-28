# SmartHomeADFramework
This repository contains the supplementary materials, documentation for the research paper:

**"Smart Home Testbed for Benchmarking Anomaly Detection"**  


## Overview

This paper introduces a comprehensive smart home testbed for evaluating anomaly detection (AD) techniques. It highlights:
- The importance of robust testbeds in AD evaluation.
- Novel frameworks for multi-metric assessments.
- Detailed anomaly profiling.

## Key Features of the Testbed
- **Comprehensive Protocol Coverage**: Supports Wi-Fi, BLE, Zigbee, and Z-wave.
- **Real-world Scenarios**: Emulates smart home conditions with diverse IoT devices.
- **Anomaly Profiling**: Details characteristics, system impacts, and user consequences.
- **Multi-metric Evaluation**: Assesses accuracy, computational overhead, and user impact.


## Requirements
- Python 3.8+
- Docker
- OpenWRT-compatible router
- Additional hardware: Zigbee dongles, BLE sniffers, etc.


## Sections:
### 1. **[Data Acquisition and Preprocessing](data_acquisition_and_preprocessing/README.md)**
A comprehensive guide of how to collect and preprocess data from the smart home testbed, focusing on Wi-Fi, Zigbee, Z-wave, and BLE communication protocols.

### 2. **[Anomaly Profiles](anomaly_profiles/README.md)**
Detailed profiles for anomalies across various communication protocols:
- [Wi-Fi Anomalies](anomaly_profiles/wifi_anomalies.md)
- [Zigbee Anomalies](anomaly_profiles/zigbee_anomalies.md)
- [Z-wave Anomalies](anomaly_profiles/z_wave_anomalies.md)
- [BLE Anomalies](anomaly_profiles/ble_anomalies.md)

### 3. **[Anomaly Detection Evaluation](anomaly_detection_evaluation/README.md)**
Evaluation framework for benchmarking AD techniques:
- [Baseline Establishment](anomaly_detection_evaluation/baseline_establishment.md)
- [Evaluation Metrics](anomaly_detection_evaluation/evaluation_metrics.md)
- [Case Study](anomaly_detection_evaluation/case_study.md)

### 4. **[Testbed Configuration](testbed_configuration/README.md)**
Outlines the setup and configuration of the smart home testbed for evaluating anomaly detection techniques
- [Testbed Overview](testbed_configuration/testbed_overview.md)
- [IoT Devices](testbed_configuration/iot_devices.md)
- [Controllers and Hubs](testbed_configuration/controllers_and_hubs.md)
- [Non-IoT Devices](testbed_configuration/non_iot_devices.md)
- [Software Tools](testbed_configuration/software_tools.md)


---

## Getting Started

### 1. Testbed Details
Take a look at the testbed etails at [Testbed Configuration](testbed_configuration/testbed_overview.md) which includes detail of IoT devices, controllers, and software tools.

### 2. Generate Anomalies
Refer to the [Anomaly Profiles](anomaly_profiles.md) section to generate anomalies. Example:

### 3. Evaluate Detection Techniques
Use the [Evaluation Framework](anomaly_detection_evaluation.md) to test AD techniques. Example:


---

## Contribution
We welcome contributions to improve the repository. Feel free to submit issues, suggest enhancements, or create pull requests.

### Guidelines
- Fork the repository.
- Make changes in a new branch.
- Submit a pull request with a clear description of changes.

---


## Citation
If you use this testbed or its resources in your research, please cite the accompanying paper:
```
@article{Alosaimixxxx,
  title={Smart Home Testbed for Benchmarking Anomaly Detection},
  author={Mohammed Alosaimi, Omer Rana, and Charith Perera},
  journal={xxxx},
  year={xxxx}
}
```

---

For more details, refer to the documentation files within this repository or contact the authors of the paper.

