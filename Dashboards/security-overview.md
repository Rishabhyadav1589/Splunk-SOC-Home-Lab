# Security Overview Dashboard

## Objective

Provide a high-level view of security events generated across the Windows endpoint.

---

## Dashboard Panels

- Total Events
- Top Event IDs
- Top Hosts
- Top Users
- Events Over Time
- Most Active Processes

---

## SPL Examples

### Total Events

```spl
index=windows
| stats count
```

### Top Event IDs

```spl
index=windows
| top EventCode
```

### Top Users

```spl
index=windows
| top User
```

### Events Over Time

```spl
index=windows
| timechart count
```

---

## Screenshot

Add Security Dashboard screenshot here.

---

## Outcome

Provides analysts with a quick overview of the environment.
