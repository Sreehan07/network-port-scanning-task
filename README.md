# network-port-scanning-task
network-port-scanning-task
---
# Task 1 – Local Network Port Scanning (Nmap)

## 🎯 Objective
Learn to discover open ports on devices in your local network to understand network exposure and basic recon skills.

## 🧰 Tools Used
- Kali Linux
- Nmap (v7.95)
- Python 3 HTTP Server (for test port)
- Optional: Wireshark (not used here)

---

## 🛠 Commands Executed

### 🔹 Find Local IP Range
```bash
ip a

# TCP SYN Scan (top 1000 ports)
sudo nmap -sS 192.168.0.0/24

# Full TCP Port Scan
sudo nmap -p- -sS 192.168.0.106

# Detect Services and OS on All Hosts
Detect Services and OS on All Hosts

#  UDP Port Scan (DNS, DHCP, NTP)
sudo nmap -sU -p 53,67,123 192.168.0.106

# Start Python HTTP Test Server 
sudo python3 -m http.server 8080


----
## 🔎 Results Summary

### ✅ Detected Hosts and Ports

| IP Address     | Device Type     | Open Ports                    | OS / Notes                     |
|----------------|------------------|-------------------------------|--------------------------------|
| 192.168.0.1    | TP-Link Router    | 80 (HTTP), 1900 (UPnP)        | Admin panel exposed            |
| 192.168.0.103  | Android Phone     | 8008, 8009, 8443, 9000, 9080  | Chromecast, NRDP open          |
| 192.168.0.102  | PC/Laptop         | None (all filtered)           | Likely host-based firewall     |
| 192.168.0.106  | Kali Linux (self) | 8080 (test HTTP server)       | Open during scanning phase     |

---

## 🔐 Risk Observations
- Router admin panel exposed over HTTP (unencrypted)
- UPnP enabled on router – can be abused
- Android device exposing multiple ports (Chromecast, NRDP)
- Kali box had a test HTTP server (safe for testing)

---

## 📁 Files Included
- `network_scan.txt`: Full Nmap scan of subnet
- `http_server_scan.txt`: HTTP server scan output
- `screenshots/`: Terminal screenshots of scans

---

## 📄 Conclusion
This task demonstrates core recon skills with Nmap. I learned to:
- Enumerate IP ranges
- Perform TCP & UDP port scans
- Detect services & OS fingerprints
- Analyze open ports and assess risk

---

## 👤 Author
Akavaram Sreehan

