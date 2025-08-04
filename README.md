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
```bash
sudo nmap -sS -A -T4 -oX scan_report.xml 10.0.2.1/24
xsltproc scan_report.xml -o network_report.html

