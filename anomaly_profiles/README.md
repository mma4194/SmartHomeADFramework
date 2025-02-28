# Anomaly Profiles for Smart Home Testbed

## Overview
This section provides detailed profiles of anomalies used in the smart home testbed, categorized by communication protocols. Each profile includes:
- Definition and purpose of the anomaly.
- Required tools and hardware.
- Step-by-step implementation guide.
- Characteristics, system impact, and user impact.
- Detection features for identifying the anomaly.

---

## Anomaly Profiles

The repository includes detailed profiles for anomalies across the following categories:

- **[Wi-Fi Anomalies](wifi_anomalies.md)**
  - Examples: De-authentication attacks, Evil Twin, Reconnaissance, etc.
- **[Zigbee Anomalies](zigbee_anomalies.md)**
  - Examples: Jamming, Packet Injection, etc.
- **[Z-wave Anomalies](z_wave_anomalies.md)**
  - Examples: Jamming, Packet Injection, etc.
- **[BLE Anomalies](ble_anomalies.md)**
  - Examples: Reconnaissance, Jamming, etc.

---

## Common Pitfalls and Recommendations

| Pitfall                           | Recommendation                                              |
|-----------------------------------|-------------------------------------------------------------|
| **User perspective overlooked**   | Involve users to assess the impact of anomalies on their experience.|
| **Network feature reliance**      | Incorporate IoT-specific features (e.g., device behavior, state changes).|
| **Anomaly uniformity assumption** | Use multiple tools to generate the same anomaly for diversity.|

---

## Acknowledgments
These anomaly profiles are based on extensive research to replicate real-world scenarios in IoT environments. Special thanks to contributors for their insights into anomaly detection and generation.

