# Windows Persistence Investigation — Investigation Notes

## 1. Investigation Objective

The objective of this investigation was to examine common Windows locations associated with automatic execution and persistence.

The investigation was conducted on a controlled Windows 7 virtual machine.

---

## 2. Startup Program Investigation

### Tool Used

```text
msconfig

### Investigation

The System Configuration utility was opened and the **Startup** tab was reviewed.

### Observation

No startup entries were displayed during the investigation.

### Security Relevance

Startup entries can be reviewed during endpoint investigations to identify programs configured to launch automatically when Windows starts.

### Evidence

![Startup Programs](./screenshots/01-startup-programs.png)

---

## 3. Scheduled Task Investigation

### Tool Used

```text
taskschd.msc

### Investigation

Windows Task Scheduler was opened and the **Task Scheduler Library** was reviewed.

### Observation

No scheduled tasks were displayed in the selected library during the investigation.

### Security Relevance

Scheduled tasks can be used for legitimate administrative functions as well as automatic execution. Unexpected tasks should be investigated using their task name, trigger, action, executable path, user context, and creation or modification details.

### Evidence

![Scheduled Tasks](./screenshots/02-scheduled-tasks.png)

---

## 4. Registry Run Key Investigation

### Registry Location

```text
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Run

```

Then paste everything below:

````markdown
### Investigation

The Registry Editor was opened and the specified Run key was examined.

### Observation

No configured Run entry was displayed in the examined key.

### Security Relevance

Registry Run keys are common locations that can configure programs to execute automatically when a user logs on.

### Evidence

![Registry Run Keys](./screenshots/03-registry-run-keys.png)

---

## 5. Windows Services Investigation

### Tool Used

```text
services.msc
```

### Investigation

The Windows Services console was opened and service status and startup types were reviewed.

### Observation

Multiple services with **Automatic** and **Manual** startup types were observed.

### Security Relevance

Windows services can start automatically or on demand. During a security investigation, unusual services should be correlated with their executable path, service account, timestamps, and other endpoint telemetry.

### Evidence

![Windows Services](./screenshots/04-services-investigation.png)

---

## 6. Evidence Summary

| Evidence | Result |
|---|---|
| Startup Programs | No entries displayed |
| Scheduled Tasks | No tasks displayed in selected library |
| Registry Run Key | No configured Run entry displayed |
| Windows Services | Multiple Automatic and Manual services observed |

---

## 7. Analyst Assessment

The investigated Windows 7 system did not show configured entries in the examined startup, scheduled-task, or Registry Run locations at the time of investigation.

The Services console contained multiple services with Automatic and Manual startup types.

The observations alone do not establish malicious activity. Further investigation would be required to determine whether any unusual persistence mechanism exists.

Useful additional evidence could include:

- Service executable paths
- File hashes
- Process creation events
- Windows Event Logs
- User account activity
- File creation and modification timestamps
- Network connections
- Sysmon telemetry

---

## 8. MITRE ATT&CK Mapping

The investigation areas are related to several MITRE ATT&CK techniques:

### T1547 — Boot or Logon Autostart Execution

Relevant to mechanisms that automatically execute programs during system boot or user logon.

### T1053 — Scheduled Task/Job

Relevant to scheduled execution mechanisms.

### T1543 — Create or Modify System Process

Relevant to persistence involving Windows services and other system processes.

The exact technique depends on the specific persistence mechanism and evidence identified.

---

## 9. Investigation Workflow

```text
Identify Persistence Locations
        ↓
Collect Evidence
        ↓
Review Configuration
        ↓
Identify Anomalies
        ↓
Correlate With Other Telemetry
        ↓
Document Findings
```

---

## 10. Ethical Scope

This investigation was conducted in a controlled virtual machine environment for cybersecurity education.

No unauthorized systems were accessed or modified.

The investigation was limited to defensive analysis of the Windows endpoint.

---

## Conclusion

This investigation demonstrated a basic defensive approach to examining common Windows persistence locations.

The investigation covered startup programs, scheduled tasks, Registry Run keys, and Windows services.

The collected evidence provides a baseline for understanding how persistence-related configurations can be reviewed during a Windows endpoint investigation.

