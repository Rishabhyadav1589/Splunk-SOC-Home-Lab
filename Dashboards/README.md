# 📊 Splunk Dashboards

## Overview

This directory contains the dashboards developed for the **Splunk SOC Home Lab**. These dashboards provide real-time visibility into security events collected from Windows endpoints using **Sysmon** and **Windows Event Logs**.

The dashboards are designed to help Security Operations Center (SOC) analysts quickly identify suspicious activities, investigate alerts, and monitor the overall health of the environment.

---

# Objectives

- Monitor Windows security events
- Visualize endpoint activity
- Detect suspicious PowerShell execution
- Track authentication events
- Identify unusual process creation
- Monitor DNS activity
- Improve threat hunting efficiency

---

# Available Dashboards

## 1. Security Overview

Provides a high-level summary of all security events.

### Panels

- Total Events
- Top Event IDs
- Events Over Time
- Top Users
- Top Hosts
- Top Processes

---

## 2. Authentication Monitoring

Monitors Windows authentication activity.

### Panels

- Successful Logins
- Failed Logins
- Login Trend
- Top Target Accounts
- Top Source Hosts

### Windows Event IDs

- 4624 – Successful Login
- 4625 – Failed Login

### MITRE ATT&CK

- T1078 – Valid Accounts
- T1110 – Brute Force

---

## 3. PowerShell Monitoring

Monitors PowerShell execution.

### Panels

- Total PowerShell Events
- Top Users
- Most Executed Commands
- PowerShell Timeline

### Windows Event IDs

- 4104 – PowerShell Script Block Logging

### MITRE ATT&CK

- T1059.001 – PowerShell

---

## Dashboard Features

- Real-time Monitoring
- Interactive Panels
- SPL-based Searches
- Incident Investigation Support
- Threat Hunting Ready
- Easy-to-read Visualizations

---

# Data Sources

The dashboards use the following log sources:

- Windows Security Logs
- Sysmon Operational Logs
- Windows Event Logs

---

# Technologies Used

- Splunk Enterprise
- Splunk Search Processing Language (SPL)
- Windows 10
- Sysmon
- Splunk Universal Forwarder
- VirtualBox

---

# Dashboard Workflow

Windows Endpoint

↓

Sysmon

↓

Windows Event Logs

↓

Splunk Universal Forwarder

↓

Splunk Enterprise

↓

Dashboards

↓

Threat Hunting & Investigation

---

# Screenshots

Dashboard screenshots are available in the **dashboard-screenshots** folder.

Example:
![Dashboard](Screenshots/dashboard-1.png)

```

├── security-overview.png
├── authentication-dashboard.png
├── powershell-dashboard.png
```

---

# Future Improvements

The following dashboards will be added in future updates:

- Process Creation Dashboard
- DNS Monitoring Dashboard
- Network Connections Dashboard
- Registry Activity Dashboard
- MITRE ATT&CK Dashboard
- Threat Hunting Dashboard

---

# Conclusion

These dashboards provide a centralized view of security events within the Splunk SOC Home Lab. They enable analysts to monitor endpoint activity, investigate suspicious behavior, and improve detection capabilities using practical, real-world security monitoring techniques.
