# Linux User & Privilege Security Audit — Investigation Notes

## 1. Investigation Objective

The objective of this investigation was to perform a basic security audit of user privileges and sudo configuration on a Kali Linux system.

The investigation focused on sudo privileges, sudoers configuration, privileged groups, SUID binaries, and root account configuration.

---

## 2. Sudo Privileges Investigation

### Command Used

```bash
sudo -l

### Investigation

The `sudo -l` command was used to identify the commands that the current user is permitted to execute with elevated privileges.

### Observation

The command displayed the sudo privileges configured for the current user.

### Security Relevance

Reviewing sudo privileges helps determine which administrative operations can be performed by a user.

### Evidence

![Sudo Privileges](./screenshots/01-sudo-privileges.png)

---

## 3. Sudoers Configuration Investigation

### Command Used

```bash
sudo cat /etc/sudoers

### Investigation

The main sudoers configuration file was reviewed to understand the rules controlling administrative privileges.

### Observation

The configuration displayed the defined sudo policies and privilege rules.

### Security Relevance

The sudoers file controls which users and groups can execute commands with elevated privileges.

### Evidence

![Sudoers Configuration](./screenshots/02-sudoers-configuration.png)

---

## 4. Sudo Group Investigation

### Command Used

```bash
getent group sudo

### Investigation

The `sudo` group was reviewed to identify users belonging to the group.

### Observation

The command displayed the members of the sudo group.

### Security Relevance

Membership in administrative groups can provide users with elevated privileges and should be reviewed during security audits.

### Evidence

![Sudo Group Members](./screenshots/03-sudo-group-members.png)

---

## 5. SUID Binary Investigation

### Command Used

```bash
find /usr/bin /usr/sbin -perm -4000 -type f 2>/dev/null

### Investigation

The command was used to identify SUID-enabled executable files in common system directories.

### Observation

The command displayed executables configured with the SUID permission.

### Security Relevance

SUID binaries can execute with the permissions of their file owner. Unexpected or vulnerable SUID binaries may require further security investigation.

### Evidence

![SUID Binaries](./screenshots/04-suid-binaries.png)

---

## 6. Sudoers Directory Investigation

### Command Used

```bash
sudo ls -la /etc/sudoers.d/

### Investigation

The `/etc/sudoers.d/` directory was reviewed for additional sudo configuration files.

### Observation

The directory contents were examined to identify additional sudo configuration files.

### Security Relevance

Additional sudo configuration files can contain privilege rules that affect administrative access.

### Evidence

![Sudoers Directory](./screenshots/05-sudoers-directory.png)

---

## 7. Sudo Version Investigation

### Command Used

```bash
sudo -V

### Investigation

The installed sudo version and configuration information were reviewed.

### Observation

The command displayed the installed sudo version and related configuration details.

### Security Relevance

Identifying software versions helps establish the security context of an endpoint and can support further vulnerability assessment.

### Evidence

![Sudo Version](./screenshots/06-sudo-version.png)

---

## 8. Root Account Status Investigation

### Command Used

```bash
sudo passwd -S root

### Investigation

The status of the root account password configuration was reviewed.

### Observation

The command displayed the current password status of the root account.

### Security Relevance

Root account configuration is an important part of Linux privilege security and should be reviewed during endpoint audits.

### Evidence

![Root Account Status](./screenshots/07-root-account-status.png)

---

## 9. Privileged Groups Investigation

### Command Used

```bash
getent group adm
getent group wheel

### Investigation

The `adm` and `wheel` groups were reviewed to identify their configured membership.

### Observation

The commands displayed the membership information for the selected privileged groups.

### Security Relevance

Privileged groups can provide additional access to administrative or security-related resources and should be reviewed during security assessments.

### Evidence

![Privileged Groups](./screenshots/08-privileged-groups.png)

---

## 10. System SUID Binary Investigation

### Command Used

```bash
find /bin /sbin /usr/bin /usr/sbin -perm -4000 -type f 2>/dev/null

### Investigation

A broader search was performed across common system binary directories to identify SUID-enabled executables.

### Observation

The command displayed SUID-enabled binaries located in the specified system directories.

### Security Relevance

Reviewing SUID binaries across common system locations provides additional visibility into programs capable of running with elevated file-owner privileges.

### Evidence

![System SUID Binaries](./screenshots/09-system-suid-binaries.png)

---

## 11. Additional Sudo Configuration Investigation

### Command Used

```bash
sudo find /etc/sudoers.d -maxdepth 1 -type f -ls

### Investigation

The `/etc/sudoers.d` directory was examined for individual sudo configuration files.

### Observation

The command displayed any files present within the sudo configuration directory.

### Security Relevance

Additional sudo configuration files can introduce privilege rules and should be reviewed as part of a complete sudo security audit.

### Evidence

![Sudoers Files](./screenshots/10-sudoers-files.png)

---

## 12. Evidence Summary

| Investigation Area | Evidence |
|---|---|
| Sudo Privileges | Current user's allowed sudo operations reviewed |
| Sudoers Configuration | Main sudo configuration reviewed |
| Sudo Group | Administrative group membership reviewed |
| SUID Binaries | SUID-enabled executables identified |
| Sudoers Directory | Additional sudo configuration reviewed |
| Sudo Version | Installed sudo version identified |
| Root Account | Root password status reviewed |
| Privileged Groups | `adm` and `wheel` groups reviewed |
| System SUID Binaries | SUID binaries across common directories reviewed |
| Sudoers Files | Additional sudo configuration files checked |

---

## 13. Analyst Assessment

The investigation provided an overview of privilege-related configuration on the Kali Linux endpoint.

Sudo permissions and administrative group membership were reviewed to understand elevated access.

SUID binaries were identified to establish which executables have elevated file-owner privileges.

The sudoers configuration and additional configuration directory were also examined to provide visibility into privilege management.

These observations provide baseline information for further defensive Linux endpoint investigations.

---

## 14. Learning Outcomes

Through this investigation, I practiced:

- Linux privilege auditing
- Sudo privilege analysis
- Sudoers configuration review
- Administrative group analysis
- SUID binary identification
- Root account status verification
- Linux security documentation
- Defensive endpoint investigation

---

## 15. Ethical Scope

This investigation was performed on a controlled Kali Linux system for cybersecurity education.

No unauthorized systems were accessed or tested.

The commands were used only for local defensive security auditing.

---

## Conclusion

This Linux user and privilege security audit demonstrated how standard Linux command-line tools can be used to review administrative privileges, sudo configuration, privileged groups, root account status, and SUID binaries.

The investigation provides a practical foundation for understanding privilege management and identifying areas that may require further defensive security review.
