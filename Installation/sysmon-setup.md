# Sysmon Installation

## Objective

Install Sysmon to generate detailed Windows telemetry for security monitoring.

---

# Why Sysmon?

Sysmon extends native Windows logging by recording detailed system activity.

It captures:

- Process Creation
- Network Connections
- DNS Queries
- Registry Changes
- File Creation Time
- Process Access

---

# Download Sysmon

Download Sysmon from Microsoft Sysinternals.

---

# Install Sysmon

Open Command Prompt as Administrator.

```
Sysmon64.exe -accepteula -i sysmonconfig.xml
```

---

# Verify Installation

```
sc query Sysmon64
```

Expected Result

```
STATE : RUNNING
```

---

# Verify Events

Open

```
Event Viewer

Applications and Services Logs

Microsoft

Windows

Sysmon

Operational
```

---

# Generate Test Events

Open PowerShell.

Run:

```
whoami

ipconfig

ping google.com

nslookup google.com

Get-Process
```

These commands should generate Sysmon events.

---

# Verify in Splunk

Search

```
index=windows sourcetype=XmlWinEventLog:Microsoft-Windows-Sysmon/Operational
```

Expected Result

Events appear successfully.

---

# Screenshots

- Sysmon Installed
- Event Viewer
- Splunk Search Result

---

# Outcome

Sysmon is successfully installed and sending endpoint telemetry to Splunk.
