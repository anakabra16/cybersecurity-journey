# Day 03 — Windows Security Fundamentals

## Overview

Hands-on practice with basic Windows security and system-monitoring commands to understand users, privileges, processes, network connections, and services.

## Objectives

- Identify Windows OS information
- Examine the current user's privileges and group memberships
- Review running processes
- Identify active TCP connections
- Understand basic Windows security monitoring

## Commands Practiced

| Command | Purpose |
|---|---|
| `systeminfo` | View Windows system information |
| `whoami /all` | View current user, groups, privileges and security information |
| `Get-Process` | List and analyze running processes |
| `Get-NetTCPConnection` | Examine active TCP connections |
| `Get-Service` | View Windows services |

## Evidence Collected

### 1. System Information
Verified the Windows operating system version and system architecture.

Screenshot:
`01-system-information.png`

### 2. User and Privileges
Examined the current Windows user account, group memberships and assigned privileges.

Screenshot:
`02-user-and-privileges.png`

### 3. Running Processes
Reviewed active processes and their CPU usage.

Screenshot:
`03-running-processes.png`

### 4. Active Network Connections
Examined established TCP connections and the associated process IDs.

Screenshot:
`04-active-network-connections.png`

## Security Relevance

Understanding normal Windows processes, users, privileges and network connections is important for security monitoring and incident investigation.

These commands provide basic endpoint visibility that can help an analyst identify unusual processes, unexpected network connections, or suspicious account activity.

## Learning Outcome

This exercise provided practical experience with Windows endpoint enumeration and basic security analysis using native PowerShell and Windows commands.

## Ethical Scope

All commands were executed on my own controlled Windows laboratory environment for cybersecurity learning purposes.
