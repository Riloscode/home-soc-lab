# ✅ Network Visibility Validation (Zeek)

We verified that Zeek captures live network traffic and generates structured logs on the active network interface (`enp0s1`).

---

## 🔎 Test Method

A live capture was initiated using the Zeek container with the following command:

```bash
zeek -i enp0s1 local
Test traffic was then generated using basic commands like:
curl http://example.com
ping 8.8.8.8
```

📁 Logs Captured
Zeek generated the following logs under /pcap and exported them to the mounted host directory ./zeek-logs/:
  conn.log – Network connection summaries
  dns.log – DNS requests and responses
  http.log – HTTP transaction summaries (triggered by curl)

🧠 Sample Log Insight
A parsed summary from conn.log revealed active local devices and external connections:
192.168.x.x      # Likely router
192.168.x.x0     # Other LAN device
192.168.x.x2     # This Zeek VM
Zeek also recorded metadata such as byte counts, ports, protocols, and session durations.

✅ Result
Zeek is fully operational and providing deep network visibility from traffic captured on enp0s1.
Logs are structured, accessible, and reflect real network activity within the lab.
