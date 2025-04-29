# 🔧 Security Onion VM Setup – Install Steps

This guide outlines the steps I followed to install and configure Security Onion in a UTM-based virtual machine for my home SOC lab.

---

## 🖥️ Environment
- **Host Machine:** macOS (M2 Pro)
- **Virtualization:** UTM
- **Guest OS:** Security Onion ISO (latest version)
- **Network Mode:** Bridged (to capture local LAN traffic)

---

## 📥 Step 1: Download Security Onion
- Visit: [https://securityonionsolutions.com/software](https://securityonionsolutions.com/software)
- Download the latest **ISO** image (use the ISO, not OVA).

---

## 🛠️ Step 2: Create the UTM VM
1. Open UTM → click **Create a New Virtual Machine**.
2. Select **Virtualize → Linux → Boot ISO Image**.
3. Attach the Security Onion ISO.
4. Set resources:
   - **Memory:** 8–12 GB (minimum)
   - **CPUs:** 2–4
   - **Disk:** 100+ GB
5. Set **Network Interface** to **Bridged Mode** (important for traffic capture).

---

## ⚙️ Step 3: Install Security Onion
1. Boot the VM using the ISO.
2. Choose **Install Security Onion** from the menu.
3. Follow the on-screen installer (default options are fine for testing).
4. After install, reboot the VM and eject the ISO.

---

## 🔐 Step 4: Initial Configuration
After reboot:
1. Login to the system using the credentials you created.
2. Run:
   ```bash
   sudo sosetup

During setup, select the following options:
Mode: Evaluation Mode (for lab testing)
Tools to Enable: Zeek, Suricata, and Elastic Stack
Passwords: Use default passwords or set your own secure credentials

📡 Step 5: Verify Network Visibility
Confirm that your bridged network adapter is capturing traffic.
Use another device on your LAN to generate traffic (browse, stream, etc.).
Open Security Onion dashboards:
  Kibana
  Squert
Validate that network logs, alerts, and traffic flows are being collected.

✅ Next Steps
Deploy Nessus in a separate VM to simulate vulnerabilities and scanning activity.
Analyze generated logs in:
  Zeek
  Suricata
  Elastic/Kibana dashboards
Export screenshots and analysis results for GitHub documentation.

🗒️ Notes
If no traffic is detected, check:

VM network adapter settings (ensure Bridged mode is active).
Local firewall settings (temporary disable for testing if needed).
Monitor system performance and adjust VM resources if necessary for stability.
