# Investigation 02 — PowerShell Process Creation

## Objective
Detect and investigate PowerShell process creation using Sysmon Event ID 1.

## Lab Environment
- Operating System: Windows 11
- Activity Type: Controlled local lab activity
- Sysmon Event ID: 1

## Detection
A controlled PowerShell process was launched with a test command.

Sysmon recorded the process creation event, including the executable path, process ID, user, integrity level, command line, and parent process information.

## Evidence
- Image: C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe
- Process ID: 23236
- User: DESKTOP-CORDS1J\user
- Integrity Level: High
- Command Line: powershell.exe -NoProfile -Command "Write-Output SOC-Test"

## Investigation
Sysmon Event ID 1 provides process creation telemetry. PowerShell activity should be investigated in context because PowerShell is a legitimate Windows administration tool that can also be used by attackers.

The observed PowerShell execution was intentionally generated for this controlled laboratory.

## MITRE ATT&CK
- Technique: T1059.001 — PowerShell

## Analyst Assessment
The activity was benign because it was intentionally generated for the laboratory. In a real SOC environment, the analyst would examine the command line, parent process, user, execution time, and related events to determine whether the PowerShell activity was suspicious.

## Evidence Screenshot
`../screenshots/04-powershell-process-creation.png`

## Conclusion
Sysmon successfully captured PowerShell process creation and demonstrated the value of process-level telemetry during SOC investigations.
