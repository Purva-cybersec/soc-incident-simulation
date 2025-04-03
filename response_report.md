# 🚨 Incident Response Report – Suspicious Login + Lateral Movement

## 🆔 Incident ID: SOC-2025-0315-001  
**Analyst:** Purva Rumde
**Date:** March 15, 2025  
**Status:** Escalated & Contained

---

## 📝 Executive Summary

A login from an unfamiliar foreign IP address was observed for the user `j.smith@company.com` during routine SOC monitoring. Subsequent activity included access to multiple sensitive files via SMB and execution of PowerShell commands, including contact with an external domain and a local privilege escalation attempt.

This behavior was outside the user’s normal activity profile and occurred outside business hours. Based on timeline correlation and threat analysis, the incident was classified as **high severity** and escalated to Tier 2 for deeper investigation.

---

## 🔍 Investigation Summary

**Key findings:**
- Geolocation analysis confirmed login from São Paulo, Brazil (first seen)
- PowerShell script activity indicated account enumeration and C2 communication
- File access patterns matched typical data collection behavior
- `Add-LocalGroupMember` command confirmed privilege escalation

**Tools used:**
- Splunk (log analysis and search)
- GeoIP Lookup
- MITRE ATT&CK Framework

---

## ⚠️ Classification

- **Category:** Unauthorized Access → Internal Recon → Privilege Escalation  
- **Severity:** High  
- **Status:** Contained  
- **MITRE TTPs:** T1078, T1087, T1136.001, T1059.001, T1071.001

---

## 🛡️ Response Actions

| Action | Status |
|--------|--------|
| Disabled user account `j.smith@company.com` | ✅ Completed |
| Blocked IP `189.23.54.18` at network edge firewall | ✅ Completed |
| Notified Tier 2 SOC team | ✅ Completed |
| Preserved logs and evidence for forensics | ✅ Completed |
| Verified no lateral access to other user accounts | ✅ Completed |

---

## ✅ Recommendations

- Enforce MFA on all user accounts, especially externally accessible ones  
- Deploy anomaly-based login alerts (geo + time)  
- Restrict PowerShell access to admin-only use cases  
- Audit admin group changes regularly  
- Educate employees on phishing, credential hygiene, and suspicious login alerts

---

## 📎 Supporting Artifacts

- [Incident Timeline](./incident_timeline.md)  
- [MITRE Mapping](./mitre_mapping.md)  
- [Log Samples](./log_samples/)  
- [Splunk Screenshots](./screenshots/)  
