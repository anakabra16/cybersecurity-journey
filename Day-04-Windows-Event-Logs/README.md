# Day 04 — Windows Event Logs & Security Monitoring

## Overview

Day 04 focuses on Windows Event Logs and native Windows security monitoring.

The objective was to understand how Windows records security-relevant activities such as authentication events, account management activity, and process creation, and how these events can be investigated using PowerShell.

---

## Objectives

- Understand the Windows Security Event Log
- Identify important Windows Security Event IDs
- Investigate failed logon activity
- Investigate successful logon activity
- Identify user account creation events
- Investigate process creation events
- Examine Windows audit policies
- Generate controlled activity for security investigation
- Practice a basic SOC investigation workflow

---

## Lab Environment

| Component | Details |
|---|---|
| Operating System | Windows 11 |
| Environment | Controlled personal cybersecurity lab |
| Tools | PowerShell, Windows Event Viewer, Audit Policy |
| Purpose | Cybersecurity learning and defensive security monitoring |

All activities were performed on a controlled personal laboratory environment.

---

## Windows Security Event IDs Investigated

| Event ID | Activity | Security Relevance |
|---|---|---|
| **4625** | Failed Logon | Helps identify unsuccessful authentication attempts |
| **4624** | Successful Logon | Records successful authentication activity |
| **4720** | User Account Created | Provides visibility into account creation |
| **4688** | Process Creation | Provides visibility into newly created processes |

---

# Commands Practiced

## 1. Identify Security Event Logs

```powershell
Get-WinEvent -ListLog * | Where-Object LogName -like "*Security*" | Select-Object LogName,RecordCount

2. View Recent Security Events
Get-WinEvent -LogName Security -MaxEvents 10 | Select-Object TimeCreated,Id,ProviderName,Message

3. Investigate Failed Logons — Event ID 4625
Get-WinEvent -FilterHashtable @{LogName='Security'; Id=4625} -MaxEvents 5 | Select-Object TimeCreated,Id,Message

4. Investigate Successful Logons — Event ID 4624
Get-WinEvent -FilterHashtable @{LogName='Security'; Id=4624} -MaxEvents 5 | Select-Object TimeCreated,Id,Message

5. Investigate Account Creation — Event ID 4720
Get-WinEvent -FilterHashtable @{LogName='Security'; Id=4720} -MaxEvents 5 | Select-Object TimeCreated,Id,Message

6. Investigate Process Creation — Event ID 4688
Get-WinEvent -FilterHashtable @{LogName='Security'; Id=4688} -MaxEvents 5 | Select-Object TimeCreated,Id,Message

7. Check Process Creation Audit Policy
auditpol /get /subcategory:"Process Creation"

8. Generate Controlled Process Activity
Start-Process notepad.exe

9. Retrieve a Process Creation Event
Get-WinEvent -FilterHashtable @{LogName='Security'; Id=4688} -MaxEvents 1 | Select-Object TimeCreated,Id,Message

10. View Detailed Process Creation Information
Get-WinEvent -FilterHashtable @{LogName='Security'; Id=4688} -MaxEvents 1 | Format-List TimeCreated,Id,ProviderName,Message

11. Check User Account Management Auditing
auditpol /get /subcategory:"User Account Management"
