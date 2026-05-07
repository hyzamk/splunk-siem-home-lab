#  Splunk SIEM Home Lab: Windows Log Monitoring & Threat Detection


![](screenshots/splunk_banner.jpg)


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


#  Tools Used

- Splunk Enterprise
- Splunk Universal Forwarder
- Oracle VirtualBox
- Windows 10
- Kali Linux
- SPL (Search Processing Language)


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
```

#  Project Implementation Steps
Below are key steps taken in the process

## 1. Splunk Enterprise Installation

Splunk Enterprise was installed on a Linux environment to act as the central SIEM server for log collection and analysis.

### Tasks Performed

- Downloaded Splunk Enterprise
  
  ![](screenshots/splunk_download.png)
- Installed Splunk on Linux
  
  ![](screenshots/install_splunk.png)
- Started Splunk service
- Configured administrator credentials
  
  ![](screenshots/starting_splunk.png)
- Accessed Splunk Web Interface on port 8000
  
  ![](screenshots/login_page.png)
  



## 2. Configuring Receiving Port

To allow external systems to send logs, receiving was enabled in Splunk on port 9997.

### Tasks Performed
- Opened Splunk Web
  
  ![](screenshots/dashboard-home.png)
- Navigated to:
  `Settings → Forwarding and Receiving`
- Enable receiving
  
  ![](screenshots/receiving_port.png)
- Configured port 9997
  
  ![](screenshots/receiving_port_enabled.png)



## 3. Windows Virtual Machine Setup

A Windows virtual machine was created using Oracle VirtualBox to simulate a client system generating logs.

### Tasks Performed

- Created Windows VM
  
  ![](screenshots/windows_vm.png)
- Configured RAM and processor settings
  
  ![](screenshots/vm_processor.png)
- Installed Windows operating system
  
  ![](screenshots/windows_vm1.png)
- Verified network connectivity between Linux and Windows

  ![](screenshots/vm_network.png)



## 4. Splunk Universal Forwarder Installation

Splunk Universal Forwarder was installed on the Windows machine to forward logs to the Splunk Enterprise server.

### Tasks Performed
- Downloaded Splunk Universal Forwarder
  
  ![](screenshots/splunk_forwader_download.png)
- Installed the forwarder on Windows
- Configured receiving indexer IP and port
  
  ![](screenshots/splunk_forwarder_config.png)
- Enabled Windows log forwarding



## 5. Windows Log Collection Configuration

Windows Event Logs were configured for monitoring and forwarding.

### Tasks Performed
- Enabled:
  - Security Logs
  - Application Logs
  - System Logs
- Configured `inputs.conf`
  
  ![](screenshots/security_logs_config.png)
- Restarted Splunk Forwarder service



## 6 Verifying Log Ingestion in Splunk

After configuration, logs from the Windows system were verified in Splunk using SPL queries.

### Tasks Performed
- Opened Search & Reporting
  
  ![](screenshots/datasummary1.png)

  ![](screenshots/datasummary.png)
- Searched incoming logs using:
```spl
index=*
```
- Verified Windows logs successfully appeared
  
  ![](screenshots/logs_dashboard.png)

  ![](screenshots/seurity_logs.png)
  

## 7. Failed Login Attack Simulation

A failed login scenario was simulated to generate security events for analysis.

### Tasks Performed
- Locked the Windows system
- Entered incorrect passwords multiple times
- Generated Windows Security EventCode 4625
  
  ![](screenshots/failed_login_event.png)



## 8. Threat Detection using SPL Queries

Splunk SPL queries were used to detect and analyze failed login attempts.

### Detection Query

```spl
index=* sourcetype=WinEventLog:Security EventCode=4625
```

### Tasks Performed
- Queried failed login events
- Analyzed security event details
- Observed audit failure logs

![](screenshots/4625.png)


## 9. Security Event Analysis

Collected logs were analyzed to understand login behavior and suspicious activities.

### Fields Analyzed
- EventCode
- Account_Name
- ComputerName
- Keywords
- TaskCategory
- SourceName

![](screenshots/4625_details.png)


## 10. Project Completion

The SIEM lab was successfully configured with centralized log collection, security event monitoring, and threat detection capabilities.

### Final Outcome
- Successfully collected Windows logs
- Detected failed login attempts
- Implemented a functional SIEM home lab using Splunk
  
![view full report](Splunk_Siem_Lab_Project_Report.pdf)

