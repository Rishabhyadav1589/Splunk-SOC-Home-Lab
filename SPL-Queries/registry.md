Registry Monitoring

Objective

Detect registry modifications using Sysmon.


---

SPL Query

index=windows EventCode=13  
| table _time TargetObject Image User


---

Description

Shows registry value modifications.

MITRE ATT&CK

T1112



---

Screenshot

![Network Connection Monitoring](../Screenshots/registry-1.png)

![Network Connection Monitoring](../Screenshots/registry-2.png)


---

Outcome

Registry changes can be monitored for persistence techniques.
