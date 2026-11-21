

<div align="center">



\# Wazuh SOC Home Lab



\### Windows Threat Detection \& Security Monitoring



A hands-on cybersecurity project focused on Windows endpoint monitoring, custom detection engineering, security event analysis, and MITRE ATT\&CK mapping.



!\[Wazuh](https://img.shields.io/badge/Wazuh-SIEM-005571?style=for-the-badge)

!\[Sysmon](https://img.shields.io/badge/Sysmon-Windows%20Telemetry-0078D4?style=for-the-badge)

!\[Windows](https://img.shields.io/badge/Windows-11-0078D4?style=for-the-badge)

!\[MITRE ATT\&CK](https://img.shields.io/badge/MITRE-ATT%26CK-C62828?style=for-the-badge)

!\[VirtualBox](https://img.shields.io/badge/VirtualBox-Lab-183A61?style=for-the-badge)



</div>



\---



\## Project Overview



This project implements a Windows-focused Security Operations Center (SOC) home laboratory using \*\*Wazuh SIEM\*\*, \*\*Sysmon\*\*, and Windows security auditing.



The objective is to collect and analyze endpoint security events, develop custom detection rules, and evaluate detection capabilities through controlled security simulations.



The laboratory demonstrates a practical detection engineering workflow:



\*\*Security Event Collection → Event Analysis → Detection Rules → Wazuh Alerts → Validation\*\*



\## Lab Architecture



```mermaid

flowchart LR

&#x20;   K\["Kali Linux<br/>Security Testing"]

&#x20;   W\["Windows 11<br/>Sysmon + Wazuh Agent"]

&#x20;   S\["Ubuntu 24.04<br/>Wazuh Server"]

&#x20;   D\["Wazuh Dashboard<br/>Alert Analysis"]



&#x20;   K -.->|"Controlled simulations"| W

&#x20;   W -->|"Security events<br/>TCP 1514"| S

&#x20;   S --> D



&#x20;   classDef testing fill:#fef3c7,stroke:#d97706,color:#78350f

&#x20;   classDef endpoint fill:#dbeafe,stroke:#2563eb,color:#1e3a8a

&#x20;   classDef server fill:#dcfce7,stroke:#16a34a,color:#14532d



&#x20;   class K testing

&#x20;   class W endpoint

&#x20;   class S,D server

```



The laboratory uses VirtualBox with \*\*Host-Only networking\*\* for internal communication and \*\*NAT\*\* for outbound connectivity.



\[View detailed network architecture](architecture/network-architecture.md)



\## Technology Stack



| Component | Technology | Purpose |

|:---|:---|:---|

| SIEM | Wazuh | Centralized security monitoring and alerting |

| Endpoint | Windows 11 | Monitored Windows system |

| Endpoint agent | Wazuh Agent | Event collection and file integrity monitoring |

| System monitoring | Sysmon | Process, registry, and network telemetry |

| Security auditing | Windows Event Logs | Windows security event collection |

| Server | Ubuntu 24.04 | Wazuh infrastructure |

| Testing environment | Kali Linux | Controlled security simulations |

| Virtualization | VirtualBox | Virtual laboratory infrastructure |

| Detection framework | MITRE ATT\&CK | Detection technique mapping |



\## Detection Scenarios



Eight security monitoring scenarios are documented with their respective detection logic and laboratory evidence.



| # | Detection Scenario | Focus | Documentation |

|:--:|:---|:---|:---|

| 01 | Suspicious PowerShell Execution | Process execution and script blocks | \[View scenario](attack-simulations/01-powershell.md) |

| 02 | LSASS Process Access | Credential access monitoring | \[View scenario](attack-simulations/02-lsass.md) |

| 03 | Scheduled Task Creation | Scheduled task monitoring | \[View scenario](attack-simulations/03-scheduled-tasks.md) |

| 04 | Windows Event Log Clearing | Defense evasion monitoring | \[View scenario](attack-simulations/04-event-log-clearing.md) |

| 05 | Registry Persistence | Autorun registry modifications | \[View scenario](attack-simulations/05-registry-persistence.md) |

| 06 | System Reconnaissance | Account discovery commands | \[View scenario](attack-simulations/06-system-reconnaissance.md) |

| 07 | Network Scanning | Blocked TCP traffic and scan indicators | \[View scenario](attack-simulations/07-network-scanning.md) |

| 08 | File Integrity Monitoring | File creation, modification, and deletion | \[View scenario](attack-simulations/08-file-integrity-monitoring.md) |



\[Explore all detection scenarios](attack-simulations/README.md)



\## MITRE ATT\&CK Coverage



Custom Wazuh detection rules are mapped to relevant MITRE ATT\&CK techniques.



| Technique | MITRE ATT\&CK ID | Detection Focus |

|:---|:---|:---|

| OS Credential Dumping: LSASS Memory | T1003.001 | Suspicious LSASS access |

| PowerShell | T1059.001 | Suspicious PowerShell activity |

| Registry Run Keys / Startup Folder | T1547.001 | Registry-based persistence |

| Scheduled Task | T1053.005 | Scheduled task creation |

| Clear Windows Event Logs | T1070.001 | Windows event log clearing |

| Local Account | T1087.001 | Account discovery |

| Network Service Discovery | T1046 | Network scanning indicators |



> MITRE ATT\&CK mappings describe the behavior monitored by the detection rules. An alert does not, by itself, prove malicious activity.



\## Detection Evidence



The laboratory documentation includes Wazuh alert screenshots covering:



\- Suspicious PowerShell execution and script blocks

\- LSASS process access

\- Scheduled task activity

\- Windows event log clearing

\- Registry autorun modifications

\- Account discovery

\- Network scanning indicators

\- File integrity monitoring



Evidence is presented within the individual scenario documentation.



\## Repository Structure



```text

wazuh-soc-homelab/

├── architecture/

│   └── network-architecture.md

├── configs/

│   ├── sysmon/

│   ├── wazuh/

│   └── windows/

├── rules/

│   └── soc\_lab\_rules.xml

├── attack-simulations/

│   ├── 01-powershell.md

│   ├── 02-lsass.md

│   ├── 03-scheduled-tasks.md

│   ├── 04-event-log-clearing.md

│   ├── 05-registry-persistence.md

│   ├── 06-system-reconnaissance.md

│   ├── 07-network-scanning.md

│   ├── 08-file-integrity-monitoring.md

│   └── README.md

└── screenshots/

```



\## Key Learning Outcomes



\- Deployment and configuration of a Windows-focused SIEM laboratory

\- Centralized Windows event collection using Wazuh

\- Sysmon-based endpoint monitoring

\- Custom Wazuh detection rule development

\- Security event investigation and alert analysis

\- Detection mapping to MITRE ATT\&CK

\- Controlled simulation and evidence-based validation

\- File integrity monitoring on Windows



\## Scope and Disclaimer



This project is intended for educational and defensive cybersecurity research.



All simulations are conducted in an authorized virtual laboratory environment. The detection rules and documented alerts demonstrate monitoring capabilities under laboratory conditions and do not constitute a production-ready detection system.



\---



<div align="center">



\*\*Built as a personal cybersecurity engineering project.\*\*



\*Windows Security Monitoring · Detection Engineering · SOC Operations\*



</div>



