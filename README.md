# Smart Medical System: Real-Time Biomedical Monitoring and Response for Smart Cities

This repository contains the implementation of a distributed Internet of Medical Things (IoMT) ecosystem designed for remote patient monitoring. This system addresses the latency and single-point-of-failure risks of cloud-only solutions by utilizing a decentralized edge computing architecture.

**Key Features & Architecture**

* **Multi-Tiered Topology:** Built with independent ESP32-WROOM edge nodes for signal acquisition and a centralized Raspberry Pi 5 gateway for data aggregation, decision-making, and GUI visualization.

* **Deterministic Performance:** Runs FreeRTOS on the edge nodes with preemptive scheduling to guarantee high-fidelity 100 Hz sensor sampling without being blocked by network delays.

* **Efficient Connectivity:** Utilizes the lightweight MQTT protocol (via a HiveMQ cloud broker) to securely transmit data across disparate Wi-Fi networks at a 1 Hz reporting rate.

* **Edge Signal Processing:** Applies a First-Order IIR Low-Pass Filter directly on the edge nodes to remove high-frequency noise and motion artifacts from raw photoplethysmogram (PPG) data.

* **Automated Emergency Feedback Loop:** Features a medical decision engine that evaluates heart rate, SpO2, and temperature against nested thresholds to instantly detect and prioritize critical states, triggering automated alerts and bidirectional hardware actuation.
