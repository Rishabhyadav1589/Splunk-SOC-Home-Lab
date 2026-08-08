# MITRE ATT&CK Mapping

## Overview

This directory documents the mapping between security detections in the Splunk SOC Home Lab and the MITRE ATT&CK framework.

MITRE ATT&CK mapping helps analysts understand which adversary behaviors can be detected by the implemented security controls.

---
## Screenshot

## Objectives

- Map detections to MITRE ATT&CK techniques
- Understand attacker behavior
- Improve detection coverage
- Support threat hunting
- Standardize security investigations

---

## Detection Coverage

The current lab focuses on:

- Authentication activity
- PowerShell execution
- Process creation
- DNS activity
- Network connections
- Registry modifications

---

## MITRE Mapping

| Detection | Event ID | Technique | ID |
|---|---:|---|---|
| Failed Login | 4625 | Brute Force | T1110 |
| Successful Login | 4624 | Valid Accounts | T1078 |
| PowerShell | 4104 | PowerShell | T1059.001 |
| Process Creation | 1 | Command and Scripting Interpreter | T1059 |
| DNS Query | 22 | DNS | T1071.004 |
| Network Connection | 3 | Application Layer Protocol / Network Activity | T1071 / T1049 |
| Registry Modification | 13 | Modify Registry | T1112 |

---

## Detection Workflow

```text
Windows / Sysmon Event
        ↓
Splunk Index
        ↓
SPL Detection
        ↓
Alert
        ↓
MITRE ATT&CK Mapping
        ↓
Investigation
        ↓
Incident Response
```

---

## Future Improvements

- Add more MITRE ATT&CK techniques
- Improve detection coverage
- Add correlation rules
- Develop risk-based detections
- Create a dedicated MITRE ATT&CK dashboard

---

## Conclusion

MITRE ATT&CK mapping provides a structured way to evaluate the detection capabilities of this Splunk SOC Home Lab and identify areas for future improvement.
