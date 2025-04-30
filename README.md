# SOC Lab – Home Security Monitoring Environment

## 📌 Overview
This project documents my hands-on home lab setup for practicing Security Operations Center (SOC) skills using real-world tools like **Security Onion**, **Zeek**, **Nessus**, and **Wireshark**. The goal is to simulate a monitored environment for detecting, analyzing, and responding to suspicious network activity.
## 📚 Table of Contents
- [Overview](#overview)
- [Tools Used](#tools-used)
- [Screenshots](screenshots/screenshots.md)
- [Lab Setup](setup/install_steps.md)
- [Skills Practiced](#skills-practiced)
- [Future Additions](#future-additions)
- [Contact](#contact)


---

## 🛠️ Tools Used
- **Security Onion** – All-in-one SOC platform for intrusion detection and log analysis
- **Zeek (formerly Bro)** – Network traffic analysis
- **Nessus** – Vulnerability scanner
- **Wireshark** – Deep packet inspection
- **VirtualBox/UTM** – Virtualization for isolated lab environments

---

## 📷 Screenshots
Screenshots of the lab setup and alert analysis will be added soon, including:
- UTM
- 
  ![VM Setup Example](screenshots/vm-config-1.png)
- Security Onion dashboard
- Zeek log entries
- Detected threats (e.g., DNS tunneling, port scans)

📌 Stay tuned — this section will be updated as I capture and document key moments from the lab.


---

## ⚙️ Lab Setup
- UTM-based VM running Security Onion
- Bridged NIC to monitor real network traffic
- Logging configured for Zeek, Suricata, and syslog sources
- Nessus scans against local devices for detection practice

---

## 🔎 What I Learned
- Configuring and tuning IDS tools (Zeek, Suricata)
- Identifying suspicious DNS and HTTP traffic
- Detecting port scans and malware signatures
- Interpreting PCAPs and alerts in Security Onion
- Creating actionable detections and reports

---

## 📁 Planned File Structure
soc-lab/ ├── README.md # Project overview and documentation ├── screenshots/ # Visuals of setup and analysis (coming soon) ├── setup/ # Setup notes, install guides, network diagram │ ├── install_steps.md # Step-by-step Security Onion VM setup │ └── network_diagram.png # Visual diagram of home lab environment ├── logs-analysis/ # Notes on analyzed alerts, suspicious traffic │ └── suspicious-traffic.md # Summary of detected activity and findings ├── scripts/ # Custom scripts used in the lab (optional) │ └── log_parser.py # Sample: Python script to parse Zeek logs

---

## 🚀 Future Additions
- Automate alert triage with Python
- Add Elastic dashboards for custom queries
- Upload Nessus vulnerability reports
- Integrate with GitHub Actions for CI learning

---
> 🚧 This project is a work in progress. Additional setup steps, screenshots, and notes will be added soon.

---
## 📫 Contact
Have feedback or questions? Feel free to connect with me on LinkedIn or open an issue.


