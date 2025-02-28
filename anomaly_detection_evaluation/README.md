# Anomaly Detection Evaluation for Smart Home Testbed

## Introduction
This section outlines a structured approach to implementing and documenting anomaly detection (AD) evaluations within a smart home testbed. The methodology is derived from a rigorous framework described in the accompanying research paper and includes steps for baseline establishment, evaluation metrics, tools, and detailed case studies. The goal is to ensure a comprehensive and reproducible evaluation process.

---

## 1. Test Scenarios for LUCID Anomaly Detection

To evaluate the LUCID anomaly detection model, the following test scenarios were implemented to replicate diverse network conditions:

### Scenarios

1. **Idle Network Traffic**:
   - **Description**: Minimal activity in the network, simulating a low-usage smart home environment.
   - **Purpose**: Establishes baseline behavior and tests model sensitivity to minimal anomalies.

2. **Busy Network Traffic**:
   - **Description**: Traffic is mirrored from multiple IoT devices, creating a high-load scenario.
   - **Purpose**: Simulates a realistic smart home environment under operational stress, testing model robustness.

3. **DDoS Attacks**:
   - **Description**: Multiple Distributed Denial of Service (DDoS) attacks with varying payload sizes are introduced.
   - **Payload Sizes Tested**:
     - **100 bytes**
     - **10,000 bytes**
     - **10,000,000 bytes**
   - **Purpose**: Assesses the model's ability to detect high-volume, malicious traffic patterns.

---

## 2. Results

The evaluation yielded the following results under different network conditions:

### Detection Rates
- **Idle Network**:
  - **Detection Rate**: 99.37% for 10,000-byte payloads, indicating high sensitivity in low-traffic environments.
- **Busy Network**:
  - **Detection Rate**: 89.87% for 10,000,000-byte payloads, demonstrating strong performance under stress.

### Computational Overhead
- **CPU Usage**:
  - Peaked at **51%** during heavy traffic, indicating significant resource demand.
- **Memory Usage**:
  - Peaked at **13%**, reflecting efficient memory management even under stress.

---

## 3. Anomaly Detection Evaluation Framework

This repository provides extensive resources for evaluating AD techniques within a smart home testbed. 

### Available Guides

- **[Baseline Establishment](baseline_establishment.md)**:
  - Details steps for creating standardized conditions to compare AD models effectively.

- **[Evaluation Metrics](evaluation_metrics.md)**:
  - Explores performance metrics such as precision, recall, F1 score, latency, and resource consumption.

- **[Case Studies](case_study.md)**:
  - Includes in-depth analysis of specific anomalies and their detection in smart home environments.

---

## 4. Common Pitfalls and Recommendations

Below are common pitfalls encountered during anomaly detection evaluations, along with suggested mitigations:

| **Pitfall**                        | **Recommendation**                                          |
|------------------------------------|-------------------------------------------------------------|
| **Incomplete data training**       | Include diverse scenarios, edge cases, and real-world conditions in the training dataset.|
| **Controller underutilization**    | Use multiple controllers to validate model consistency across device ecosystems.|
| **Accuracy-only evaluation**       | Incorporate system-level metrics, including latency, CPU usage, and memory overhead.|
| **Idle network testing only**      | Test AD techniques under both idle and busy network conditions to ensure robustness.|

---

## Additional Resources

Explore these tools and repositories to enhance your evaluation process:

- **[LUCID Model Repository](https://github.com/doriguzzi/lucid-ddos)**:
  - Official repository for implementing and testing the LUCID AD model.

- **[DDoS Testing Tool (hping3)](https://www.kali.org/tools/hping3/)**:
  - Tool for generating DDoS attacks.

---

## Acknowledgments

This evaluation framework is adapted from extensive research into anomaly detection within IoT environments. Special thanks to all contributors for their insights, case studies, and evaluation metrics, which have informed this guide.
