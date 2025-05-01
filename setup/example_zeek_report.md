# 🔍 Device Analysis Report – 192.168.x.xx

## 📌 Summary
The host at `192.168.x.xx` is confirmed **active** and exposing the following open TCP ports:

- **5000/tcp** & **7000/tcp**: RTSP service returning `403 Forbidden` with server header `AirTunes/850.19.1`.  
  ➤ Likely indicates **Apple AirPlay** (e.g., Apple TV, HomePod, or macOS device).
  
- **49152/tcp**: Open but unidentified service.  
  ➤ Possibly **ephemeral/custom** port — further investigation recommended.

---

## 📁 Zeek Log Indicators

### From `conn.log`:
- Multiple **REJ (connection refused)** TCP attempts from 192.168.x.xx targeting 192.168.x.xx on sensitive ports (e.g., `22`, `445`, `3389`, `143`, `110`, `80`, `443`, etc.)
- One **RSTO** connection to port 22 (`TCP Reset by originator`).

### From `weird.log`:
- `bad_TCP_checksum`
- `ssh_unknown_kex_algorithm` → uncommon/unsupported SSH key exchange: `sntrup761x25519-sha512@openssh.com`

---

## 🛠️ Assessment

These behaviors suggest one or more of the following:
- **Misconfigured Apple device** (e.g., AirPlay or remote management enabled).
- **Aggressive scanning or beaconing** behavior by the host.
- Potential **unauthorized activity or compromise**.

---

## ✅ Recommendations

1. **Physically identify** the device (MAC address lookup, DHCP log).
2. **Disable unnecessary services** (AirPlay, SSH, etc.).
3. **Perform endpoint antivirus/malware scan**.
4. **Check firewall rules** and limit outbound access from this host.
5. Continue **Zeek/NIDS monitoring** for any new anomalies or escalation.

---

**Analyst:** _(Riloscode)_  
**Date:** 2025-05-01  
**Environment:** SOC Home Lab – Zeek on Security Onion
