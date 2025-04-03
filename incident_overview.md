# 🛡️ Incident Overview: Suspicious Login + Lateral Movement Simulation

## 📆 Date & Time (Simulated)
March 15, 2025 – 02:12 UTC

## 👤 Analyst Role
SOC Tier 1 Analyst – Monitoring corporate authentication and file access activity.

---

## 📝 Incident Summary

During routine monitoring, a successful login from an unusual foreign IP address was detected for user `j.smith@company.com`. This was followed by access to sensitive files and PowerShell command execution. These behaviors suggested lateral movement and privilege escalation.

---

## 💻 Assets Involved

| Asset Type | Value |
|------------|-------|
| User Account | j.smith@company.com |
| Source IP | 189.23.54.18 |
| Host Accessed | FS-Server-01 |
| Protocols | SMB, PowerShell, HTTP |

---

## 🚩 Indicators of Suspicion

- 🔴 Unusual geolocation (São Paulo, Brazil)
- 🟠 Rapid access to HR, Legal, and IT shares
- 🟢 PowerShell used immediately after login
- 🔵 No MFA triggered
- 🟣 Out-of-hours access pattern
