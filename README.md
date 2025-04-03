# 🛡️ SOC Analyst Simulation: Suspicious Login + Lateral Movement Detection

This project simulates a real-world SOC (Security Operations Center) investigation of a suspicious login followed by lateral movement activity. Using synthetic logs and Splunk, I performed end-to-end detection, triage, MITRE mapping, and response documentation — just like a Tier 1 or 2 SOC analyst would.

---

## 🎯 Project Goals

- Detect suspicious login activity using authentication logs
- Investigate post-login behavior: file access + PowerShell use
- Map activity to MITRE ATT&CK TTPs
- Document the response workflow and generate a playbook
- Simulate a realistic SOC analyst workflow using Splunk

---

## 🔍 Tools Used

- **Splunk (Free Cloud)** – for log ingestion, search, and correlation  
- **MITRE ATT&CK Navigator** – to map tactics and techniques  
- **Markdown** – for structured documentation  
- **Canva** – for timeline visuals (optional)

---

## 📁 Project Structure

/soc-incident-simulation/
├── README.md
├── incident_overview.md
├── timeline.png (from Canva)
├── log_samples/
│   ├── auth_logs.csv
│   ├── smb_access_logs.csv
│   └── powershell_events.csv
├── mitre_mapping.md
├── response_report.md
└── playbook.md
└── screenshots/ 
|   ├── splunk_auth_search.png 
|   ├── splunk_smb_results.png 
|   └── splunk_ps_results.png

---

## 📑 Key Documents

- 📄 [Incident Overview](./incident_overview.md)  
- 🕒 [Timeline of Events](./incident_timeline.md)  
- 🧠 [MITRE ATT&CK Mapping](./mitre_mapping.md)  
- 🚨 [Incident Response Report](./response_report.md)  
- 📋 [SOC Playbook](./playbook.md)  

---

## 🔍 Splunk Log Analysis

This simulation used Splunk to ingest and analyze logs across:
- Authentication activity
- File share (SMB) access
- PowerShell command execution

---

### Sample Queries:
```spl
index=main sourcetype="auth_logs" user="j.smith@company.com"
index=main sourcetype="smb_logs" | stats count by file_accessed
index=main sourcetype="ps_logs" | table timestamp user command status

---

###📸 **Screenshots**:
