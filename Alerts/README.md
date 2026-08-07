# 🚨 Splunk Alerts

## Overview

This directory contains the alert configurations developed for the Splunk SOC Home Lab.

The alerts are designed to detect suspicious activities using Windows Security Logs and Sysmon events. They demonstrate how Splunk can automatically identify potential security incidents and notify analysts for further investigation.

---

# Objectives

- Detect suspicious authentication attempts
- Monitor PowerShell activity
- Identify unusual process execution
- Monitor DNS activity
- Reduce Mean Time to Detect (MTTD)
- Support incident response

---

# Available Alerts

| Alert | Description | MITRE ATT&CK |
|--------|-------------|--------------|
| Failed Login Alert | Detect multiple failed logins | T1110 |
| PowerShell Alert | Detect PowerShell execution | T1059.001 |
| Suspicious Process Alert | Detect unusual process creation | T1059 |
| DNS Monitoring Alert | Detect suspicious DNS queries | T1071.004 |

---

# Alert Workflow

Windows Endpoint

↓

Sysmon / Windows Security Logs

↓

Splunk Universal Forwarder

↓

Splunk Enterprise

↓

SPL Detection Query

↓

Alert Triggered

↓

SOC Analyst Investigation

---

# Alert Components

Each alert includes:

- Objective
- SPL Query
- Trigger Condition
- Alert Severity
- MITRE ATT&CK Mapping
- Investigation Steps
- Expected Outcome

---

# Technologies Used

- Splunk Enterprise
- Splunk SPL
- Windows Event Logs
- Sysmon
- MITRE ATT&CK Framework

---

# Future Improvements

- Email Notifications
- Risk-Based Alerting
- Alert Correlation
- Custom Detection Rules
- Dashboard Integration

---
# Screenshots

![alert](/Screenshots/alert-1.png)
![alert](/Screenshots/alert-2.png)
![alert](/Screenshots/alert-3.png)


# Conclusion

These alerts demonstrate practical SIEM detection engineering skills and provide automated detection capabilities for common attack techniques in a SOC environment.
