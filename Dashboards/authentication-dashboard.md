# Authentication Dashboard

## Objective

Monitor successful and failed authentication attempts.

---

## Dashboard Panels

- Successful Logins
- Failed Logins
- Failed Login Trend
- Top Target Accounts
- Top Source Hosts

---

## SPL Queries

### Successful Login

```spl
index=windows EventCode=4624
| stats count by Account_Name
```

### Failed Login

```spl
index=windows EventCode=4625
| stats count by Account_Name
```

### Login Trend

```spl
index=windows (EventCode=4624 OR EventCode=4625)
| timechart count
```

---

## Screenshot

Add dashboard screenshot here.

---

## MITRE ATT&CK

- T1078 Valid Accounts
- T1110 Brute Force

---

## Outcome

Helps identify brute-force attempts and unusual login behavior.
