# Investigation 01 — Failed Logon Detection

## Objective
Detect and investigate a failed Windows authentication attempt using Windows Security Event ID 4625.

## Lab Environment
- Operating System: Windows 11
- Activity Type: Controlled local lab activity
- Account: user
- Event ID: 4625

## Detection
A controlled incorrect-password login attempt was generated using the Windows `runas` command.

Windows Security Event ID 4625 was then queried from the Security event log.

## Evidence
- Event ID: 4625
- Event Type: Audit Failure
- Task: Logon
- Account Name: user
- Domain: DESKTOP-CORDS1J
- Logon Type: 2
- Failure Reason: Unknown user name or bad password
- Status: 0xC000006D
- Sub Status: 0xC000006A
- Caller Process: C:\Windows\System32\svchost.exe

## Investigation
The event represents a failed authentication attempt. The activity was intentionally generated as part of this controlled SOC laboratory.

The event demonstrates how Windows Security logs can provide authentication telemetry that a SOC analyst can investigate for repeated or suspicious login failures.

## MITRE ATT&CK
- Technique: T1078 — Valid Accounts

## Analyst Assessment
The observed event was benign because it was intentionally generated for this laboratory. In a real environment, repeated Event ID 4625 events would require additional investigation, including the source account, source host, timing, frequency, and surrounding authentication events.

## Evidence Screenshot
`../screenshots/03-event-4625-failed-logon.png`

## Conclusion
Windows Event ID 4625 successfully demonstrated detection of a failed authentication attempt and provided useful evidence for SOC investigation.
