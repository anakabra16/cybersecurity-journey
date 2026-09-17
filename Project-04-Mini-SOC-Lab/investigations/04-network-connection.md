# Investigation 04 — Network Connection

## Objective
Detect and investigate network connection telemetry using Sysmon Event ID 3.

## Lab Environment
- Operating System: Windows 11
- Activity Type: Controlled local lab activity
- Sysmon Event ID: 3

## Detection
Sysmon Network Connection monitoring was enabled and controlled network activity was generated.

Sysmon recorded a network connection associated with the Chrome process.

## Evidence
- Event ID: 3
- Process: chrome.exe
- Process ID: 27324
- User: DESKTOP-CORDS1J\user
- Protocol: UDP
- Source IP: 192.168.7.56
- Destination IP: 192.168.7.1
- Destination Port: 53
- Initiated: false

## Process Correlation
The network event was correlated with PID 27324.

The corresponding process was:

`C:\Program Files\Google\Chrome\Application\chrome.exe`

## Investigation
The event demonstrates how Sysmon can associate network activity with the process responsible for the connection.

Port 53 is associated with DNS traffic. The observed connection was associated with Chrome and occurred within the controlled laboratory environment.

## Analyst Assessment
The observed connection was consistent with legitimate browser/network activity in the lab. A real SOC investigation would correlate destination reputation, process ancestry, user context, frequency, and other endpoint/network events.

## Evidence Screenshots
- `../screenshots/08-sysmon-event-3-network-connection.png`
- `../screenshots/09-process-correlation-chrome.png`

## Conclusion
Sysmon Event ID 3 successfully provided network telemetry and allowed the connection to be correlated with the responsible process.
