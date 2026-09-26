# Linux Process Security Audit — Investigation Notes

## 1. Investigation Objective

The objective of this investigation was to perform a basic security audit of running processes on a Kali Linux system.

The investigation focused on running processes, process hierarchy, and CPU resource usage.

---

## 2. Running Processes Investigation

### Command Used

```bash
ps aux

### Investigation

The `ps aux` command was used to display currently running processes on the system.

### Observation

The command displayed running processes along with information such as the process owner, process ID, CPU usage, memory usage, and command.

### Security Relevance

Reviewing running processes helps analysts understand the current activity on a Linux endpoint and identify processes that may require further investigation.

### Evidence

![Running Processes](./screenshots/01-running-processes.png)

---

## 3. Process Tree Investigation

### Command Used

### Investigation

The process tree was reviewed to understand the parent-child relationships between running processes.

### Observation

The command displayed processes in a hierarchical structure along with their process IDs.

### Security Relevance

Process relationships can help analysts understand how processes were started and identify unusual parent-child relationships that may require further investigation.

### Evidence

![Process Tree](./screenshots/02-process-tree.png)

---

## 4. Process Resource Usage Investigation

### Command Used

```bash
ps aux --sort=-%cpu | head -15

```bash
pstree -p

### Investigation

The command was used to identify processes with higher CPU usage.

### Observation

The output displayed the processes using the highest CPU resources at the time of investigation.

### Security Relevance

Unexpectedly high resource usage may indicate applications requiring further investigation. Resource usage alone does not establish malicious activity.

### Evidence

![Process Resource Usage](./screenshots/03-process-resource-usage.png)

---

## 5. Evidence Summary

| Investigation Area | Observation |
|---|---|
| Running Processes | Active processes identified |
| Process Tree | Parent-child process relationships reviewed |
| Resource Usage | Higher CPU-consuming processes identified |

---

## 6. Analyst Assessment

The investigation provided a basic overview of processes currently running on the Kali Linux endpoint.

Running processes were reviewed to understand active system activity.

The process tree was examined to understand process relationships.

CPU usage was also reviewed to identify processes consuming higher system resources.

The observations alone do not establish malicious activity. Any suspicious process would require additional investigation and validation.

---

## 7. Security Relevance

Process security auditing can help identify:

- Unexpected processes
- Unusual process relationships
- High-resource-consuming processes
- Unknown applications
- Processes requiring additional investigation

Each observation should be validated in its system context before being considered a security issue.

---

## 8. Learning Outcomes

Through this investigation, I practiced:

- Linux process enumeration
- Process hierarchy analysis
- Process ID identification
- CPU resource analysis
- Defensive endpoint investigation
- Security-focused documentation

---

## 9. Ethical Scope

This investigation was performed on a controlled Kali Linux system for cybersecurity education.

No unauthorized systems were accessed or tested.

The commands were used only for local defensive security auditing.

---

## Conclusion

This Linux process security audit demonstrated how standard Linux tools can be used to examine running processes, process relationships, and system resource usage.

The investigation provides a foundation for understanding Linux endpoint activity and performing basic defensive process analysis.
