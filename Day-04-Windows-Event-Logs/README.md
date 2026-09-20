# Day 04 — Windows Event Logs & Security Monitoring

## Overview

Hands-on practice with Windows Security Event Logs and native auditing tools to understand how security-relevant activities are recorded and investigated.

This exercise focused on identifying authentication activity, account management events, and process creation events using PowerShell and Windows Audit Policy.

## Objectives

- Understand the Windows Security Event Log
- Identify important security-related Event IDs
- Investigate failed and successful logons
- Identify account creation events
- Investigate process creation events
- Check Windows audit policies
- Generate controlled security activity for investigation
- Practice basic SOC-style event analysis

## Lab Environment

- Operating System: Windows 11
- Environment: Controlled personal cybersecurity laboratory
- Tools: PowerShell, Windows Event Logs, Audit Policy
- Kali Linux: Not required for this exercise

## Security Event IDs Investigated

| Event ID | Activity | Security Relevance |
|---|---|---|
| 4625 | Failed Logon | Can indicate incorrect credentials or repeated authentication attempts |
| 4624 | Successful Logon | Records successful authentication activity |
| 4720 | User Account Created | Helps identify new account creation |
| 4688 | Process Creation | Provides visibility into newly created processes |

## Commands Practiced

### Security Event Logs

```powershell
Get-WinEvent -ListLog * | Where-Object LogName -like "*Security*" | Select-Object LogName,RecordCount
## Evidence Collected

### 1. Security Event Logs

![Security Event Logs](screenshots/01-security-event-logs.png)

### 2. Recent Security Events

![Recent Security Events](screenshots/02-recent-security-events.png)

### 3. Failed Logon — Event ID 4625

![Event 4625 Failed Logon](screenshots/03-event-4625-failed-logon.png)

### 4. Successful Logon — Event ID 4624

![Event 4624 Successful Logon](screenshots/04-event-4624-successful-logon.png)

### 5. Account Creation — Event ID 4720

![Event 4720 Account Creation](screenshots/05-event-4720-account-creation.png)

### 6. Process Creation — Event ID 4688

![Event 4688 Process Creation](screenshots/09-event-4688-controlled-process.png)

### 7. User Account Management Audit Policy

![User Account Management Audit Policy](screenshots/11-user-account-management-audit-policy.png)
