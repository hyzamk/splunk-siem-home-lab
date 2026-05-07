#  Splunk SIEM Home Lab: Windows Log Monitoring & Threat Detection

A hands-on SIEM home lab built using **Splunk Enterprise** and **Splunk Universal Forwarder** for centralized log collection, monitoring, and basic threat detection.

This project demonstrates how Windows Event Logs can be collected, forwarded, and analyzed using Splunk SPL queries to identify suspicious activities such as failed login attempts.

---

#  Project Overview

This lab simulates a basic SOC (Security Operations Center) environment where logs from a Windows machine are monitored through Splunk SIEM running on Linux.

The project includes:
- Splunk Enterprise deployment
- Universal Forwarder configuration
- Windows Event Log collection
- Security event monitoring
- Failed login detection
- Basic attack simulation

---

#  Architecture

```text
      Windows Machine
             ↓
   Splunk Universal Forwarder
             ↓
         Port 9997
             ↓
Splunk Enterprise Server (Linux)
             ↓
 Search, Monitoring & Detection
