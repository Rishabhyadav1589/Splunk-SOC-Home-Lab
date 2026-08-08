---

# 2. `incident-01-failed-login.md`

```markdown
# Incident 01 - Multiple Failed Login Attempts

## Incident Overview

| Field | Details |
|---|---|
| Incident ID | INC-001 |
| Detection | Multiple Failed Logins |
| Severity | Medium |
| Event ID | 4625 |
| MITRE ATT&CK | T1110 - Brute Force |
| Status | Investigated |

---

## 1. Alert Description

The Splunk alert detected multiple failed Windows authentication attempts against a monitored account.

---

## 2. Detection Query

```spl
index=windows EventCode=4625
| stats count by Account_Name host
| where count >= 5
