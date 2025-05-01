# ✅ IDS/IPS Validation (Suricata)

We verified that Suricata is actively monitoring network traffic and triggering alerts based on signature matches.

---

## 🔎 Test Method

We used the public test domain [`http://testmyids.com`](http://testmyids.com), which simulates malicious behavior designed to trigger IDS rules.

---

## 🛑 Alert Captured (from `fast.log`)

05/01/2025-17:47:46.670397 [] [1:2100498:7] GPL ATTACK_RESPONSE id check returned root [] [Classification: Potentially Bad Traffic] [Priority: 2] {TCP} 217.160.0.187:80 -> 192.168.4.42:38928


---

## 🧠 Meaning

- Suricata matched this traffic against the **GPL ATTACK_RESPONSE** ruleset.
- The alert indicates a response containing "`id` returned `root`", a known indicator of command injection or info disclosure.
- Confirms Suricata is actively inspecting packets on interface `enp0s1`.

---

## ✅ Result

Suricata is operational and correctly generating alerts in response to test traffic.

---

