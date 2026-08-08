# MITRE ATT&CK Detection Mapping

## 1. Brute Force

### Technique

**T1110 - Brute Force**

### Detection

Multiple failed authentication attempts.

### Windows Event ID

```text
4625
```

### SPL

```spl
index=windows EventCode=4625
| stats count by Account_Name host
| where count >= 5
```

### SOC Use Case

Used to identify potential password guessing and brute-force activity.

---

# 2. Valid Accounts

### Technique

**T1078 - Valid Accounts**

### Detection

Successful authentication activity.

### Windows Event ID

```text
4624
```

### SPL

```spl
index=windows EventCode=4624
| stats count by Account_Name host
```

### SOC Use Case

Can help identify suspicious use of legitimate credentials when correlated with unusual source hosts, times, or authentication patterns.

---

# 3. PowerShell

### Technique

**T1059.001 - PowerShell**

### Detection

PowerShell Script Block Logging.

### Windows Event ID

```text
4104
```

### SPL

```spl
index=windows EventCode=4104
| table _time host User ScriptBlockText
```

### SOC Use Case

Used to investigate PowerShell execution and identify potentially suspicious commands or scripts.

---

# 4. Command and Scripting Interpreter

### Technique

**T1059 - Command and Scripting Interpreter**

### Detection

Process creation telemetry.

### Sysmon Event ID

```text
1
```

### SPL

```spl
index=windows EventCode=1
| table _time host User Image ParentImage CommandLine
```

### SOC Use Case

Allows analysts to investigate process execution and parent-child process relationships.

---

# 5. DNS

### Technique

**T1071.004 - DNS**

### Detection

DNS query activity.

### Sysmon Event ID

```text
22
```

### SPL

```spl
index=windows EventCode=22
| table _time host User QueryName Image
```

### SOC Use Case

DNS telemetry can provide useful context when investigating suspicious domain resolution and potential command-and-control behavior.

---

# 6. Network Activity

### Detection

Network connection telemetry.

### Sysmon Event ID

```text
3
```

### SPL

```spl
index=windows EventCode=3
| table _time host User Image DestinationIp DestinationPort
```

### SOC Use Case

Used to investigate outbound network connections and correlate network activity with process execution.

---

# 7. Modify Registry

### Technique

**T1112 - Modify Registry**

### Detection

Registry value modification.

### Sysmon Event ID

```text
13
```

### SPL

```spl
index=windows EventCode=13
| table _time host User Image TargetObject
```

### SOC Use Case

Registry telemetry can assist in identifying suspicious configuration changes and potential persistence activity.

---

# Detection Coverage Matrix

| Technique | ID | Telemetry | Detection |
|---|---|---|---|
| Brute Force | T1110 | Windows Security | Failed Login |
| Valid Accounts | T1078 | Windows Security | Successful Login |
| PowerShell | T1059.001 | PowerShell Logging | PowerShell Activity |
| Command & Scripting Interpreter | T1059 | Sysmon | Process Creation |
| DNS | T1071.004 | Sysmon | DNS Query |
| Network Activity | T1049 / T1071 | Sysmon | Network Connection |
| Modify Registry | T1112 | Sysmon | Registry Modification |

---

# Detection Coverage Goal

The lab will continue to expand its MITRE ATT&CK coverage by adding detections for additional attacker behaviors.

Future areas include:

- Persistence
- Credential Access
- Discovery
- Execution
- Defense Evasion
- Command and Control
- Lateral Movement

---

# Conclusion

The MITRE ATT&CK mapping provides a clear relationship between endpoint telemetry, SPL detections, and adversary techniques.

This mapping can be used during threat hunting and incident investigations to understand attacker behavior and identify detection gaps.
