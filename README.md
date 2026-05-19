# Home SOC Lab: UTM, Ubuntu ARM, Docker, Wazuh, Zeek, Suricata, and Kibana

## Project Summary

This repository documents a hands-on Security Operations Center lab built to practice SOC analyst skills, network monitoring, alert review, and security documentation.

The lab was built on a Mac with an Apple Silicon M2 chip using UTM to virtualize Ubuntu ARM64. Core security tools are deployed and tested using Linux and Docker-based workflows.

## Objective

The goal of this project is to build practical cybersecurity experience by deploying security monitoring tools, capturing network traffic, reviewing alerts, and documenting investigation workflows.

This lab helps develop skills related to:

- SOC analysis
- Network monitoring
- Intrusion detection
- Log analysis
- Alert triage
- Incident documentation
- Linux administration
- Docker-based tool deployment

## Lab Environment

| Component | Details |
|---|---|
| Host OS | macOS on Apple Silicon M2 |
| Virtualization | UTM |
| Guest OS | Ubuntu 22.04.5 ARM64 Server |
| CPU | 4 cores |
| Memory | 8–12 GB |
| Disk | 84 GB |
| NIC 1 | Bridged management interface |
| NIC 2 | Emulated monitoring interface |

## Tools Used

| Tool | Purpose |
|---|---|
| Wazuh | Log collection, SIEM-style visibility, endpoint monitoring, and alert correlation |
| Zeek | Network protocol analysis and log generation |
| Suricata | IDS/IPS testing, packet inspection, and alert generation |
| Kibana | Dashboarding and visual analysis |
| Elasticsearch | Log and event data backend |
| Docker | Containerized tool deployment |
| Nmap | Port scanning and service fingerprinting |
| ZMap | High-speed network scanning for lab testing |
| tcpdump | Packet capture and traffic inspection |
| Linux | System administration and security tooling |

## Lab Architecture

The lab uses a virtualized Ubuntu server as the core SOC environment. The VM is configured with separate network interfaces for management and monitoring.

- Management interface: used for system updates, package installation, and administrative access
- Monitoring interface: used for traffic capture and network visibility
- Docker services: used to deploy and manage security tools
- Security tools: used to collect logs, inspect traffic, generate alerts, and support investigations

## Key Activities Completed

- Set up an isolated Ubuntu VM environment using UTM
- Installed and configured Docker
- Installed and tested Wazuh agent functionality
- Captured and reviewed live network traffic
- Used Zeek logs such as `conn.log` for network behavior analysis
- Tested Suricata IDS/IPS alerting
- Performed targeted scans using Nmap and ZMap
- Investigated rejected connections and abnormal events
- Grouped agents in Wazuh for organized log management
- Used dashboards to review and correlate security events

## Skills Demonstrated

- SOC lab design
- Linux administration
- Docker deployment
- Network monitoring
- IDS/IPS concepts
- Log analysis
- Alert triage
- Packet capture
- Troubleshooting
- Security documentation
- Technical writing

## Documentation

- [Home SOC Lab Setup Guide](setup/)
- IDS/IPS validation notes
- Wazuh configuration notes
- Network monitoring notes

## Security Notes

This lab is intended for isolated educational use only.

- Do not expose lab services directly to the internet
- Use sanitized screenshots when publishing findings
- Avoid uploading real IP addresses, credentials, tokens, or sensitive network information
- Keep lab activity limited to systems you own or have permission to test

## Current Status

This project is currently in progress. The lab is being expanded to include more detection testing, endpoint logging, alert review, and incident-style writeups.

## Planned Improvements

- Add Windows endpoint logging
- Forward Windows logs into Wazuh
- Add Sysmon configuration and event analysis
- Simulate brute-force login activity
- Create SOC investigation reports from generated alerts
- Add screenshots of dashboards and detection results
- Add sample incident reports under a `reports/` folder
