# Linux System Information Audit — Investigation Notes

## 1. Investigation Objective

The objective of this investigation was to collect basic system information from a Kali Linux endpoint.

The investigation focused on system information, kernel version, and system uptime.

---

## 2. System Information Investigation

### Command Used

```bash
uname -a

### Investigation

The `uname -a` command was used to collect general information about the Linux operating environment.

### Observation

The command displayed system and kernel-related information.

### Security Relevance

System information helps analysts understand the operating environment during a security assessment.

### Evidence

![System Information](./screenshots/01-system-information.png)

---

## 3. Kernel Version Investigation

### Command Used

```bash
uname -r

### Investigation

The kernel version of the Kali Linux system was identified.

### Observation

The command displayed the currently running Linux kernel version.

### Security Relevance

Knowing the running kernel version helps establish the software environment of a Linux endpoint and can support further security assessment.

### Evidence

![Kernel Version](./screenshots/02-kernel-version.png)

---

## 4. System Uptime Investigation

### Command Used

```bash
uptime

### Investigation

The system uptime and current load information were reviewed.

### Observation

The command displayed how long the system had been running along with system load information.

### Security Relevance

System uptime provides useful context during endpoint investigations and can help analysts understand the current operational state of a system.

### Evidence

![System Uptime](./screenshots/03-system-uptime.png)

---

## 5. Evidence Summary

| Investigation Area | Observation |
|---|---|
| System Information | General Linux system information identified |
| Kernel Version | Running kernel version identified |
| System Uptime | System uptime and load information reviewed |

---

## 6. Analyst Assessment

The investigation provided a basic overview of the Kali Linux operating environment.

System information was collected to establish the system context.

The running kernel version was identified, and system uptime and load information were reviewed.

These observations provide useful baseline information for further defensive security investigations.

---

## 7. Learning Outcomes

Through this investigation, I practiced:

- Linux system information gathering
- Kernel version identification
- System uptime analysis
- Basic endpoint reconnaissance
- Security-focused documentation

---

## 8. Ethical Scope

This investigation was performed on a controlled Kali Linux system for cybersecurity education.

No unauthorized systems were accessed or tested.

The commands were used only for local defensive system auditing.

---

## Conclusion

This Linux system information audit demonstrated how simple command-line tools can be used to establish a basic understanding of a Linux endpoint and its operating environment.
