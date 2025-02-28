# Case Study

## 1. DDoS Attack Evaluation

### Setup
This case study evaluates the efficiency of LUCID, a lightweight deep learning solution, for detecting DDoS attacks in a smart home network.

#### Key Components
- **AD Technique**: [LUCID](https://github.com/doriguzzi/lucid-ddos)
  - A lightweight deep learning-based solution designed for detecting DDoS attacks.
- **Data Sources**:
  - **Live Traffic**: Captured using [Wireshark](https://www.wireshark.org/).
  - **DDoS Attacks**: Simulated using [hping3](https://www.kali.org/tools/hping3/).

---

### Methodology
1. **Implementation**:
   - Set up LUCID following the official implementation guidelines available in its [repository](https://github.com/doriguzzi/lucid-ddos).
2. **Traffic Simulation**:
   - Capture live traffic from a smart home testbed using Wireshark.
   - Simulate DDoS attacks using hping3 with varying payload sizes (e.g., 100 bytes, 10,000 bytes, 10,000,000 bytes).
3. **Evaluation**:
   - Analyze LUCID’s performance under different network conditions.
   - Record detection rates and computational metrics, including CPU and memory usage.

---

### Results

#### Detection Performance
- **Network Conditions**:
  - High detection accuracy in idle networks.
  - Performance degradation observed in busy networks with high traffic volumes.

#### Computational Metrics
- **Impact of Payload Size**:
  - Larger payloads resulted in increased computational overhead.
  - Peak CPU usage: 51%.
  - Memory consumption: 13%.

---

## Additional Resources
- [LUCID Repository](https://github.com/doriguzzi/lucid-ddos)
- [Wireshark Tutorials](https://www.wireshark.org/docs/)
- [Hping3 Documentation](https://tools.kali.org/information-gathering/hping3)

---

## Acknowledgments
This case study leverages LUCID for DDoS detection and evaluates its performance using realistic network traffic scenarios. Special thanks to the contributors for their valuable insights and tools.
