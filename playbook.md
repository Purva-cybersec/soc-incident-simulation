# 📋 SOC Playbook: Suspicious Login + Lateral Movement

## 🎯 Purpose
This playbook outlines the standard response procedure for SOC analysts when detecting and investigating suspicious logins, particularly those followed by internal activity such as file access and PowerShell use.

---

## 🛠️ Required Tools

- Splunk (or other SIEM)
- GeoIP lookup tool (MaxMind, AbuseIPDB)
- MITRE ATT&CK Navigator
- AD/LDAP access for group membership checks
- PowerShell logging enabled (ScriptBlock + Module)

---

## 🚨 Trigger / Detection Scenarios

| Trigger | Description |
|--------|-------------|
| Login from unusual geolocation | e.g., foreign country never associated with user |
| No MFA challenge recorded | Especially if MFA is normally required |
| Sudden SMB/file access to sensitive shares | e.g., HR, Legal, IT |
| PowerShell activity shortly after login | Recon, privilege escalation, C2 |
| Self-added to administrator groups | Detected via audit logs or AD logs |

---

## 🧪 Triage Process (Tier 1)

1. **Search for user login events**
   - `index=main sourcetype=auth_logs user="j.smith@company.com"`
2. **Review source IP**
   - Geolocation lookup, check if it’s new or malicious
3. **Check file access**
   - Look for sensitive files touched in a short time window
4. **PowerShell monitoring**
   - Search for unusual or external communications
5. **Correlate timeline**
   - Determine if actions follow attack patterns

---

## 🧯 Response Actions (Tier 2 or Escalated Tier 1)

| Action | Description |
|--------|-------------|
| Disable user account | Immediately cut access to prevent escalation |
| Block IP address | Block at firewall or proxy |
| Preserve logs | For forensics and root cause analysis |
| Notify IT/security lead | Escalate per IR policy |
| Create incident ticket | Assign severity and link to SOC tracker |

---

## 🧠 Recommendations & Follow-up

- Enable geo-aware login alerting
- Implement MFA and session validation
- Enable full PowerShell logging
- Use automated alerts for rapid login + internal file access
- Educate staff on credential protection

---

## 📎 Related Files

- [Incident Overview](./incident_overview.md)  
- [Incident Timeline](./incident_timeline.md)  
- [MITRE Mapping](./mitre_mapping.md)  
- [Response Report](./response_report.md)  
- [Log Samples](./log_samples/)  
