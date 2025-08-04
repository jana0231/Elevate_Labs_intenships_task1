# 🛡️ Cybersecurity Internship Task 1 – Port Scanning & Network Discovery  
**Elevate Labs Virtual Internship – Task 1 Submission**  
🔗 GitHub Repo: [jana0231/Elevate_Labs_intenships_task1](https://github.com/jana0231/Elevate_Labs_intenships_task1/)

---

## 👤 Personal Details

- **Name:** Janarthanan S
- **Role:** Cybersecurity Intern
- **Task:** Network Port Scanning & Reconnaissance
- **Date:** August 4, 2025

---

## 📌 Task Objective

To perform **active reconnaissance** on a virtualized NAT-based local network using **Nmap**, identify **live hosts** and **open ports**, and analyze potential **security exposures**. This simulates basic threat mapping within an internal environment.

---

## 🌐 Network Overview

### 💻 Environment:
| Component        | Description                          |
|------------------|--------------------------------------|
| Host OS          | Windows (assumed)                    |
| Guest OS         | Ubuntu/Kali VM via VirtualBox        |
| Network Type     | NAT (default VBox setup)             |
| Subnet Scanned   | `10.0.2.0/24`                        |
| Tool Used        | Nmap 7.95                            |

---

## ⚙️ Tools & Command Used

### ✅ Installed Tools:
- [Nmap](https://nmap.org/download.html)

### IP Discovery:
![network](/ip_discovery.png)

### 🧪 Command Executed:
---

```bash
sudo nmap -sS -A -T4 -oX scan_report.xml 10.0.2.1/24
xsltproc scan_report.xml -o network_report.html
```

## Check the report

- [Network_Report](https://github.com/jana0231/Elevate_Labs_intenships_task1/network.html)
---

## Observations & Host Analysis

🖥️ 10.0.2.1 – Virtual NAT Gateway

  - Open Port: 53/tcp (DNS)

  - OS Guess: VoIP/NAT Device

  - Risk: DNS services may be abused if unprotected.

🖥️ 10.0.2.2 – Likely Internal Guest or Service Host

  - Open Ports:

  - 135/tcp – MSRPC

  - 445/tcp – SMB (Windows file sharing)

  - 3306/tcp – MySQL 8.0.43


### Risk Factors:

- SMB vulnerable to lateral movement

- Exposed MySQL without access control is critical

- Weak or default creds may pose threats


🖥️ 10.0.2.3 – Filtered/Firewalled Host

All Ports Filtered

  - Likely hardened or protected guest

🖥️ 10.0.2.15 – Scanning Host Itself (Guest)

- All Ports Closed

- OS not fingerprinted

- No exposure detected

  
### 🛠️ Remediation Recommendations:
---
| Risk            | Recommendation                                   |
| --------------- | ------------------------------------------------ |
| Open MySQL Port | Restrict access via firewall, enable SSL & auth  |
| SMB Exposure    | Disable if unused, or restrict to internal IPs   |
| DNS Visibility  | Use internal-only DNS or block external queries  |
| OS Fingerprints | Limit excessive responses via firewall hardening |
| Host Discovery  | Deploy monitoring to detect unexpected scans     |

---

### 💡 Conclusion
---
 This task demonstrated my ability to:

- Use Nmap professionally for internal reconnaissance

- Understand network surface exposure

- Evaluate live hosts, ports, and services

- Suggest actionable remediation steps

This exercise mimics the initial steps of penetration testing or a blue team audit, critical for understanding how attackers think and how defenders should respond.
