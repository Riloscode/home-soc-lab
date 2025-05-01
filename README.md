# 🛡️ Home SOC Lab – UTM + Ubuntu ARM + Docker

This repository documents a lightweight Security Operations Center (SOC) lab built on a Mac (M2 chip) using UTM to virtualize Ubuntu ARM64, with core security tools deployed via Docker.

---

## 🔧 Project Overview

This project provides a reproducible setup for cybersecurity students, analysts, and home lab enthusiasts to:

- Deploy and test SOC tools like **Zeek**, **Suricata**, and **Kibana**
- Capture and analyze traffic from a home network
- Simulate alert generation and detection workflows

---

## 💻 Host Environment

- **Host OS**: macOS (Apple Silicon M2)
- **Virtualization Tool**: [UTM](https://mac.getutm.app)
- **Guest OS**: Ubuntu 22.04.5 ARM64 Server

---

## 📦 VM Configuration

| Component     | Value                |
|---------------|----------------------|
| CPU Cores     | 4                    |
| Memory        | 8–12 GB              |
| Disk          | 84 GB                |
| NIC 1         | Bridged (management) |
| NIC 2         | Emulated (monitoring) |

---

## 🚀 Quick Start

1. Download Ubuntu Server ARM64 ISO from [Ubuntu Releases](https://cdimage.ubuntu.com/releases/22.04/release/)
2. Create a new UTM VM using the ISO
3. Follow [Home SOC Lab Setup](./docs/Home%20Soc%20Lab%20Setup.md) to complete installation
4. Install Docker and deploy tools:
   ```bash
   sudo apt update && sudo apt upgrade -y
   sudo apt install -y docker.io
   sudo systemctl enable docker
   sudo systemctl start docker
   sudo usermod -aG docker $USER

---
📬 Contact
Feel free to open an issue or PR if you want to collaborate or report a problem!
