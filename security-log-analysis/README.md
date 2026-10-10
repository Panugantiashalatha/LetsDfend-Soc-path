# Security Log Analysis

Hands-on SOC analyst labs from the LetsDefend "Security Solutions" path. Each report reads real IDS, IPS, firewall, EDR and antivirus logs and records what happened, what it means and how an analyst would respond.

**Author:** Asha Latha Panuganti | MSc Cyber Security, Aston University

## Reports

| Lesson | Report | Logs analysed |
|---|---|---|
| Intrusion Detection System (IDS) | [PDF](reports/Intrusion_Detection_System_IDS.pdf) | Zeek HTTP, Zeek FTP |
| Intrusion Prevention System (IPS) | [PDF](reports/Intrusion_Prevention_System_IPS.pdf) | Suricata (3 alerts) |
| Firewall | [PDF](reports/Firewall.pdf) | FortiGate-format firewall log |
| Endpoint Detection and Response (EDR) | [PDF](reports/Endpoint_Detection_and_Response_EDR.pdf) | CrowdStrike (2 detections) |
| Antivirus Software (AV) | [PDF](reports/Antivirus_Software_AV.pdf) | Windows Defender |

## Key findings

| Log | Finding |
|---|---|
| Zeek HTTP | HTTP `GET` request answered with 200 OK |
| Zeek FTP | File downloaded with the `RETR` command; transfer completed |
| Suricata 1 | `net user` command ran successfully (Successful User Privilege Gain, severity 1) |
| Suricata 2 | SSLv3 connection matching the POODLE attack signature; allowed, not blocked |
| Suricata 3 | Nmap scan detected through its user agent; server answered 401 |
| Firewall | Inbound IMAP (port 143) connection denied, 0 bytes sent |
| EDR 1 | PowerShell tried to download and run `Invoke-Mimikatz`; blocked by CrowdStrike |
| EDR 2 | PowerShell tried to download `Get-System.ps1` (PowerSploit); severity High, blocked |
| Windows Defender | `executable.8180.exe` is a Trojan; the Backdoor detection is `program1` |

## Skills demonstrated

Log analysis, alert triage, network protocols (OSI model, HTTP, FTP, TLS, IMAP), EDR investigation, PowerShell attack recognition, MITRE ATT&CK mapping, malware classification, clear documentation.

## Tools

Notepad++, Zeek, Suricata, CrowdStrike Falcon, Windows Defender, LetsDefend lab environment.

## Notes

All logs come from a training lab with sample data. No real systems or credentials are involved, and lab passwords are redacted in the screenshots.
