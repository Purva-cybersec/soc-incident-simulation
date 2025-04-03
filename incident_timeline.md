# 🕒 Incident Timeline – Suspicious Login and Lateral Movement

This timeline summarizes key events observed during the investigation. Timestamps are based on log entries and Splunk queries.

| Time (UTC) | Event |
|------------|-------|
| 02:12:03 | ✅ Successful login by `j.smith@company.com` from foreign IP `189.23.54.18` |
| 02:13:45 | 🟢 Second login confirms persistent session from same IP |
| 02:14:10 | 📁 Accessed `HR/payroll.xlsx` via SMB on `FS-Server-01` |
| 02:14:25 | 📁 Accessed `Legal/contracts.docx` — uncommon access pattern |
| 02:14:58 | ⚠️ Accessed `IT/admin_creds.txt` — high-sensitivity file |
| 02:15:32 | 💻 Executed PowerShell command: `Get-LocalUser` |
| 02:15:57 | 🌐 Ran `Invoke-WebRequest` to external URL `http://malicious-url.xyz` |
| 02:16:21 | 🚨 Added self to local admin group using PowerShell |
| 02:17:00 | 🔺 Incident escalated to Tier 2 SOC for further containment |
