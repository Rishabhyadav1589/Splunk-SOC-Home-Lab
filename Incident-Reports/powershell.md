
# 3. `incident-02-powershell.md`

```markdown
# Incident 02 - PowerShell Activity

## Incident Overview

| Field | Details |
|---|---|
| Incident ID | INC-002 |
| Detection | PowerShell Script Block |
| Severity | High |
| Event ID | 4104 |
| MITRE ATT&CK | T1059.001 - PowerShell |
| Status | Investigated |

---

## 1. Alert Description

Splunk detected PowerShell Script Block Logging activity on the monitored Windows endpoint.

---

## 2. Detection Query

```spl
index=windows EventCode=4104
| table _time host User ScriptBlockText
