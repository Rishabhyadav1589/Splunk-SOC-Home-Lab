# 5. `incident-04-process.md`

```markdown
# Incident 04 - Suspicious Process Creation

## Incident Overview

| Field | Details |
|---|---|
| Incident ID | INC-004 |
| Detection | Process Creation |
| Severity | High |
| Sysmon Event ID | 1 |
| MITRE ATT&CK | T1059 - Command and Scripting Interpreter |
| Status | Investigated |

---

## 1. Alert Description

A process creation event was identified during endpoint monitoring.

---

## 2. Detection Query

```spl
index=windows EventCode=1
| table _time host User Image ParentImage CommandLine
