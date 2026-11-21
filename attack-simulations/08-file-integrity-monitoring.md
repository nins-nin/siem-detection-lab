# File Integrity Monitoring — Wazuh SOC Home Lab

## Overview

This scenario demonstrates file integrity monitoring (FIM) using the Wazuh agent on a Windows 11 endpoint.

Wazuh monitors the `C:\SOC-Lab` directory and generates alerts when monitored files are created, modified, or deleted.

## Detection Coverage

| Rule ID | Level | Detection |
|---|---|---|
| 554 | 5 | File creation |
| 550 | 7 | File integrity checksum changed |
| 553 | 7 | File deletion |

## Validation

The Wazuh Dashboard recorded alerts for file creation, modification, and deletion within the monitored laboratory directory.

## Evidence

![Wazuh FIM alerts](screenshots/08-file-integrity-monitoring.png)

## Conclusion

File integrity monitoring generated alerts for changes to monitored files, demonstrating visibility into file creation, modification, and deletion.
