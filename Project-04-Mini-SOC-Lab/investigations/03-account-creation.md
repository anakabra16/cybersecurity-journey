# Investigation 03 — Local Account Creation

## Objective
Detect and investigate the creation of a new Windows user account using Windows Security Event ID 4720.

## Lab Environment
- Operating System: Windows 11
- Activity Type: Controlled local lab activity
- Event ID: 4720

## Detection
A temporary test account named `SOC-Test` was created using the Windows `net user` command.

Windows Security Event ID 4720 was then queried from the Security event log.

## Evidence
- Event ID: 4720
- Event Type: Audit Success
- Task: User Account Management
- Action: A user account was created
- Subject Account: user
- New Account: SOC-Test
- Primary Group ID: 513

## Investigation
Event ID 4720 provides visibility into newly created Windows accounts. Unexpected account creation can require investigation because unauthorized accounts may provide additional access.

The account in this lab was intentionally created for testing and was deleted after the investigation.

## MITRE ATT&CK
- Technique: T1136 — Create Account
- Sub-technique: T1136.001 — Local Account

## Analyst Assessment
The activity was benign because the account was intentionally created as part of the SOC laboratory and subsequently removed.

## Evidence Screenshot
`../screenshots/05-user-account-created-4720.png`

## Conclusion
Windows Event ID 4720 successfully demonstrated detection and investigation of local account creation.

