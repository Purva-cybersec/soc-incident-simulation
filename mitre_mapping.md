# 🧠 MITRE ATT&CK Mapping – Suspicious Login + Lateral Movement

This file maps the observed activity in this simulated incident to known Tactics and Techniques from the MITRE ATT&CK framework.

---

## 🔐 Initial Access

| Activity | Technique | ID | Description |
|----------|-----------|----|-------------|
| Successful login from foreign IP using valid credentials | Valid Accounts | [T1078](https://attack.mitre.org/techniques/T1078/) | Use of stolen or compromised credentials |

---

## 🖥️ Execution

| Activity | Technique | ID | Description |
|----------|-----------|----|-------------|
| PowerShell command: `Get-LocalUser` | PowerShell | [T1059.001](https://attack.mitre.org/techniques/T1059/001/) | Scripting environment used for command execution |
| PowerShell: `Invoke-WebRequest` to external URL | Command and Scripting Interpreter | [T1059](https://attack.mitre.org/techniques/T1059/) | Common way to download or communicate with external systems |

---

## 🧭 Discovery

| Activity | Technique | ID | Description |
|----------|-----------|----|-------------|
| PowerShell command `Get-LocalUser` | Account Discovery | [T1087](https://attack.mitre.org/techniques/T1087/) | Listing local accounts for privilege escalation |

---

## 📁 Collection

| Activity | Technique | ID | Description |
|----------|-----------|----|-------------|
| Access to sensitive files via SMB (`payroll.xlsx`, `admin_creds.txt`) | File and Directory Discovery | [T1083](https://attack.mitre.org/techniques/T1083/) | Identifying files of interest for exfiltration |

---

## 🔄 Lateral Movement

| Activity | Technique | ID | Description |
|----------|-----------|----|-------------|
| Added self to local Administrators group | Create Account | [T1136.001](https://attack.mitre.org/techniques/T1136/001/) | Privilege escalation by creating/adding user to privileged group |

---

## 🌐 Command and Control (C2)

| Activity | Technique | ID | Description |
|----------|-----------|----|-------------|
| HTTP request to external domain using PowerShell | Application Layer Protocol | [T1071.001](https://attack.mitre.org/techniques/T1071/001/) | Using HTTP/S for outbound communication |

---

## 🧩 Notes

- MITRE ATT&CK provides a consistent language to describe attacker behavior
- Each mapping here can inform detection engineering, threat hunting, and SOC alert tuning
- This mapping helps justify why this incident was considered a **High-Risk Escalation**
