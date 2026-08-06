# Splunk SOC Home Lab Architecture

## Overview

This Splunk SOC Home Lab simulates a basic Security Operations Center (SOC) environment for security monitoring, threat detection, and incident investigation.

The lab collects Windows logs using Sysmon and forwards them to Splunk through the Splunk Universal Forwarder. Splunk indexes the logs, where SPL queries, dashboards, and alerts are used to detect suspicious activities.

---

## Components

### Windows 10 Virtual Machine
- Generates Windows Event Logs
- Sysmon installed for enhanced telemetry
- Splunk Universal Forwarder installed

### Sysmon
- Captures:
  - Process Creation
  - Network Connections
  - DNS Queries
  - Registry Changes
  - File Creation
  - Process Injection (where applicable)

### Splunk Universal Forwarder
- Collects Windows logs
- Sends logs securely to Splunk Enterprise

### Splunk Enterprise
- Receives and indexes logs
- Executes SPL queries
- Generates alerts
- Creates dashboards
- Supports incident investigation

---

## Data Flow

Windows VM
↓
Sysmon
↓
Windows Event Logs
↓
Splunk Universal Forwarder
↓
Splunk Enterprise
↓
Dashboards • Alerts • Threat Hunting

---

## Detection Workflow

1. Generate activity on Windows.
2. Sysmon records the event.
3. Universal Forwarder sends logs.
4. Splunk indexes the data.
5. SPL queries detect suspicious activity.
6. Alerts are generated.
7. Analyst investigates the event.

---

## Technologies Used

- Splunk Enterprise
- Splunk Universal Forwarder
- Sysmon
- Windows 10
- VirtualBox
- SPL (Search Processing Language)
- MITRE ATT&CK Framework
