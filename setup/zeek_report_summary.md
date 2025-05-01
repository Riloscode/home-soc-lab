# Zeek Traffic Summary Report

_Report generated on: May 1, 2025_

This report summarizes network traffic captured by Zeek in the home SOC lab environment.

🔒 Top Source IPs

| IP Address               | Count |
|--------------------------|-------|
| 192.168.x.x              | 32    |
| 192.168.x.x              | 25    |
| 192.168.x.x              | 25    |
| fd4c:f450::xxxx          | 24    |
| fd4c:f450::xxxx          | 24    |
| fe80::xxxx               | 12    |
| fe80::xxxx               | 12    |
| fe80::xxxx               | 11    |
| 192.168.4.x              | 9     |
| 192.168.4.x              | 8     |

🔒 Top Destination IPs

| IP Address               | Count |
|--------------------------|-------|
| ff02::fb                 | 58    |
| 224.0.0.251              | 58    |
| 239.255.2xx.2x0          | 27    |
| ff02::1                  | 24    |
| ff02::1x                 | 7     |
| ff02::1:2                | 6     |
| ff02::1:xxxx             | 5     |
| 192.168.x.xx            | 5     |
| 192.168.x.x              | 5     |
| 8.8.8.8                  | 1     |

📡 Protocols Seen

| Protocol | Count |
|----------|-------|
| UDP      | 164   |
| ICMP     | 40    |
| TCP      | 4     |


# Mini Script
#!/bin/bash

echo "===== ZEEK TRAFFIC SUMMARY =====" > zeek-summary.txt

echo -e "\n[1] Log Files:" >> zeek-summary.txt
ls -lh zeek-logs/ >> zeek-summary.txt

echo -e "\n[2] Top Source IPs:" >> zeek-summary.txt
grep -vE '^(#|uid|string)' zeek-logs/conn.log | awk '{print $3}' | sort | uniq -c | sort -nr >> zeek-summary.txt

echo -e "\n[3] Top Destination IPs:" >> zeek-summary.txt
grep -vE '^(#|uid|string)' zeek-logs/conn.log | awk '{print $5}' | sort | uniq -c | sort -nr >> zeek-summary.txt

echo -e "\n[4] Protocols Seen:" >> zeek-summary.txt
grep -vE '^(#|uid|string)' zeek-logs/conn.log | awk '{print $7}' | sort | uniq -c | sort -nr >> zeek-summary.txt

echo -e "\n[5] Sample HTTP Entries:" >> zeek-summary.txt
if [ -f zeek-logs/http.log ]; then
  head -n 5 zeek-logs/http.log >> zeek-summary.txt
else
  echo "No http.log file found." >> zeek-summary.txt
fi

echo -e "\n[✓] Report saved to zeek-summary.txt"
