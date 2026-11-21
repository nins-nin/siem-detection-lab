\# Attack Simulations — Wazuh SOC Home Lab



\## Overview



This directory documents controlled security simulations performed in the Wazuh SOC Home Lab.



The objective is to evaluate Windows security telemetry, investigate suspicious activity, and demonstrate detection capabilities using Wazuh, Sysmon, and Windows Event Logs.



\## Detection Scenarios



| # | Scenario | Monitoring Focus |

|---|---|---|

| 01 | Suspicious PowerShell Execution | Sysmon EID 1, PowerShell EID 4104 |

| 02 | LSASS Process Access | Sysmon EID 10 |

| 03 | Scheduled Task Creation | Security EID 4698, Task Scheduler EID 106 |

| 04 | Windows Event Log Clearing | Security EID 1102, System EID 104 |

| 05 | Registry Persistence | Sysmon EID 12, 13, 14 |

| 06 | System Reconnaissance | Sysmon EID 1 |

| 07 | Network Scanning | Network activity and available security telemetry |

| 08 | File Integrity Monitoring | Wazuh FIM alerts |



\## Validation Methodology



Detection scenarios are assessed using controlled actions within the isolated laboratory.



Evidence may include:



\- Windows event records

\- Sysmon telemetry

\- Wazuh security alerts

\- Custom detection rule identifiers

\- Wazuh Dashboard screenshots



The documentation distinguishes between observed endpoint activity, native Wazuh detections, custom rule matches, and logtest-based validation.



\## Detection Rules



Custom detection rules are maintained in:



`../rules/soc\_lab\_rules.xml`



\## Laboratory Architecture



Network topology and component details are documented in:



`../architecture/network-architecture.md`



