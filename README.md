#  Splunk SIEM Home Lab: Windows Log Monitoring & Threat Detection

A hands-on SIEM home lab built using **Splunk Enterprise** and **Splunk Universal Forwarder** for centralized log collection, monitoring, and basic threat detection.

This project demonstrates how Windows Event Logs can be collected, forwarded, and analyzed using Splunk SPL queries to identify suspicious activities such as failed login attempts.


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
#  Tools Used

- Splunk Enterprise
- Splunk Universal Forwarder
- Oracle VirtualBox
- Windows 10
- Kali Linux
- SPL (Search Processing Language)

---

#  Skills Learned

- SIEM Deployment & Configuration
- Centralized Log Collection
- Windows Event Log Monitoring
- Splunk Forwarder Configuration
- SPL Query Writing
- Security Event Analysis
- Failed Login Detection
- Basic Threat Detection
- SOC Monitoring Concepts
- Log Analysis & Investigation

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
