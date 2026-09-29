# Linux Disk & Storage Security Audit — Investigation Notes

## 1. Investigation Objective

The objective of this investigation was to perform a basic audit of disk usage and storage configuration on a Kali Linux system.

The investigation focused on disk space usage, mounted filesystems, and block devices.

---

## 2. Disk Usage Investigation

### Command Used

```bash
df -h

### Investigation

The `df -h` command was used to review available and used disk space on the system.

### Observation

The command displayed filesystem storage capacity, used space, available space, and usage percentages.

### Security Relevance

Disk usage monitoring helps identify storage constraints and provides useful information during Linux endpoint investigations.

### Evidence

![Disk Usage](./screenshots/01-disk-usage.png)

---

## 3. Mounted Filesystems Investigation

### Command Used

```bash
mount | head -20

### Investigation

The mounted filesystems were reviewed to understand which filesystems were currently mounted on the system.

### Observation

The command displayed mounted filesystem information.

### Security Relevance

Reviewing mounted filesystems helps analysts understand the storage resources currently accessible to the operating system.

### Evidence

![Mounted Filesystems](./screenshots/02-mounted-filesystems.png)

---

## 4. Block Devices Investigation

### Command Used

```bash
lsblk

### Investigation

The `lsblk` command was used to identify block devices and their partition structure.

### Observation

The command displayed available block devices and their associated partitions.

### Security Relevance

Block device information helps establish the disk and partition layout of a Linux endpoint and provides useful context during system investigations.

### Evidence

![Block Devices](./screenshots/03-block-devices.png)

---

## 5. Evidence Summary

| Investigation Area | Observation |
|---|---|
| Disk Usage | Filesystem storage usage reviewed |
| Mounted Filesystems | Mounted storage resources identified |
| Block Devices | Disk and partition structure identified |

---

## 6. Analyst Assessment

The investigation provided a basic overview of the storage configuration of the Kali Linux endpoint.

Disk usage was reviewed to understand available and used storage capacity.

Mounted filesystems were examined to identify currently accessible storage resources.

Block devices were also reviewed to understand the system's disk and partition structure.

The observations provide baseline information that can support further defensive endpoint investigations.

---

## 7. Learning Outcomes

Through this investigation, I practiced:

- Linux disk usage analysis
- Filesystem identification
- Mounted filesystem analysis
- Block device enumeration
- Storage-focused security documentation

---

## 8. Ethical Scope

This investigation was performed on a controlled Kali Linux system for cybersecurity education.

No unauthorized systems were accessed or tested.

The commands were used only for local defensive system auditing.

---

## Conclusion

This Linux disk and storage security audit demonstrated how standard Linux command-line tools can be used to review disk usage, mounted filesystems, and block devices.

The investigation provides a basic foundation for understanding Linux storage configuration during defensive security assessments.
