This project demonstrates the implementation of a **Network Intrusion Detection System (NIDS)** using **Snort++ (Snort 3)** on **Kali Linux**.  
The system monitors network traffic in real time and generates alerts for suspicious activities using custom detection rules.

This project was completed as part of an **internship task** to understand IDS concepts, rule-based detection, and network traffic monitoring.

---

## 🛠 Tools & Technologies
- **Snort++ (Snort 3)**
- **Kali Linux**
- **Nmap** (for testing port scans)
- **Linux Networking Utilities**

---

## ⚙️ Features
- Real-time network traffic monitoring
- Custom IDS rule creation
- ICMP (Ping) detection
- TCP SYN-based port scan detection
- Alert logging and verification

---

## 📁 Project Structure
CodeAlpha_Network_Intrusion_Detector
├── snort.lua
├── rules
│ └── local.rules
└── README.md

yaml
Copy code

---

## 🧪 Custom Rules Implemented

### ICMP Ping Detection
```snort
alert icmp any any -> any any (msg:"ICMP Ping Detected"; sid:1000001; rev:1;)
TCP Port Scan Detection
snort
Copy code
alert tcp any any -> any any (flags:S; msg:"Possible TCP Port Scan"; sid:1000002; rev:1;)
▶️ How to Run
1. Validate Configuration
bash
Copy code
sudo snort -T -c snort.lua
2. Run Snort in IDS Mode (Loopback Interface)
bash
Copy code
sudo snort -c snort.lua -i lo -A alert_fast
3. Generate Test Traffic (New Terminal)
bash
Copy code
ping localhost
nmap localhost
📊 Output & Alerts
Alerts are displayed in real time using alert_fast

Logs are stored in:

bash
Copy code
/var/log/snort/
