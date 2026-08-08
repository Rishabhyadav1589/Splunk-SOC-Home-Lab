# PowerShell Dashboard

## Objective

Monitor PowerShell execution and detect suspicious scripts.

---

## Dashboard Panels

- Total PowerShell Events
- Top Users
- Most Executed Commands
- PowerShell Activity Timeline

---

## SPL Queries

### Total Events

```spl
index=windows EventCode=4104
| stats count
```

### Top Users

```spl
index=windows EventCode=4104
| top User
```

### Timeline

```spl
index=windows EventCode=4104
| timechart count
```

---

## Screenshot

Add dashboard screenshot here.

---

## MITRE ATT&CK

- T1059.001 PowerShell

---

## Outcome

Allows analysts to quickly identify suspicious PowerShell activity.
