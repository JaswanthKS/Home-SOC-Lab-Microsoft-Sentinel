# 🛡️ Home SOC Lab - Microsoft Sentinel

## Project Overview
A fully functional Security Operations Center (SOC) lab built using Microsoft Sentinel as the SIEM platform. This project demonstrates real-world attack simulation, detection engineering, and incident response capabilities.

## 🏗️ Architecture
- **Attacker:** Kali Linux VM (192.168.1.189)
- **Target:** Windows 11 Enterprise VM (192.168.1.100)
- **SIEM:** Microsoft Sentinel (Azure - East US)
- **Log Collection:** Azure Monitor Agent via Azure Arc

## 🔧 Tools & Technologies
- Microsoft Sentinel
- Azure Arc
- Azure Monitor Agent
- Kali Linux
- Hydra (Brute Force)
- Nmap (Port Scanning)
- KQL (Kusto Query Language)
- VirtualBox

## ⚔️ Attack Scenarios
### 1. SMB Brute Force Attack
- Tool: Hydra
- Target: Windows 11 SMB (Port 445)
- Detection: High volume security events (>10/min)
- Severity: High

## 📊 Detection Rules (KQL)
### Brute Force Detection
```kql
Event
| where EventLog == "Security"
| summarize count() by Computer, bin(TimeGenerated, 1m)
| where count_ > 10
```

## 🚨 Incidents Detected
| Incident | Severity | Category | Status |
|----------|----------|----------|--------|
| Brute Force Detection - High Security Events | High | Credential Access | Detected |

## 📸 Screenshots

### Incidents Dashboard
![Incidents](screenshots/incidents-dashboard.png)

### KQL Brute Force Detection
![KQL](screenshots/kql-brute-force-detection.png)

### Heartbeat - VM Connected to Sentinel
![Heartbeat](screenshots/heartbeat.png)

### Azure Arc - VM Connected to Azure
![Azure Arc](screenshots/azure-arc.png)

## 🎓 Certifications
- SC-900: Microsoft Security Fundamentals (In Progress)
- AZ-500: Microsoft Azure Security Technologies (Planned)
