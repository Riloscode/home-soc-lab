🛠️ Home SOC Lab Setup Guide

This document provides detailed instructions for setting up a lightweight SOC (Security Operations Center) lab using UTM and Ubuntu Server (ARM64) on a macOS (Apple Silicon) host.

📦 System Requirements

Host OS: macOS (M1/M2)

Virtualization: UTM

Guest OS: Ubuntu 22.04.5 ARM64 Server

Resources:

CPU: 4 Cores

RAM: 8–12 GB

Disk: 84 GB+

Network: 2 NICs (1 for management, 1 for monitoring)

🔧 Steps to Set Up the Lab

1. Download Required ISO

Go to Ubuntu Releases

Download ubuntu-22.04.5-live-server-arm64.iso

2. Create VM in UTM

Open UTM → Create New VM → Virtualize → Linux → ARM64

Boot from the ISO image

Configure hardware:

CPU: 4 cores

Memory: 8–12 GB

Disk: 84 GB

Network: Add two NICs (first bridged, second bridged/emulated)

3. Install Ubuntu Server

Select: Try or Install Ubuntu Server

Choose: Continue without updating

Enable NIC1, disable NIC2

Skip proxy

Accept default mirror

Use entire disk with LVM (no encryption)

Create user credentials

Enable OpenSSH server

Skip Snap installs

After install, remove ISO and reboot

4. First Boot & Updates

sudo apt update && sudo apt upgrade -y

🐳 Install Docker & Configure

sudo apt install -y docker.io
sudo systemctl enable docker
sudo systemctl start docker
sudo usermod -aG docker $USER
newgrp docker

🚀 Optional Docker Tools

Zeek

Suricata

Kibana

Elasticsearch

(Docker setup for each tool can be documented in tool-specific markdown files.)

🔐 Security Best Practices

Use separate interfaces for management and monitoring

Avoid exposing the VM to the open internet

Sanitize logs and screenshots before sharing or publishing

📎 See Also

README.md – Main project summary

Docker Compose Samples – Coming soon
