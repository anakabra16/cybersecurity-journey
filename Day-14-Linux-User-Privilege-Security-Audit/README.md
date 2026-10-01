# Day 14 — Linux User & Privilege Security Audit

## Objective

The objective of this project was to perform a basic security audit of user privileges and sudo configuration on a Kali Linux system.

## Investigation Areas

- Sudo privileges
- Sudoers configuration
- Sudo group membership
- SUID binaries
- Sudo configuration directory
- Sudo version
- Root account status
- Privileged groups
- System SUID binaries
- Additional sudo configuration files

## Commands Used

- `sudo -l`
- `sudo cat /etc/sudoers`
- `getent group sudo`
- `find /usr/bin /usr/sbin -perm -4000 -type f 2>/dev/null`
- `sudo ls -la /etc/sudoers.d/`
- `sudo -V`
- `sudo passwd -S root`
- `getent group adm`
- `getent group wheel`
- `find /bin /sbin /usr/bin /usr/sbin -perm -4000 -type f 2>/dev/null`
- `sudo find /etc/sudoers.d -maxdepth 1 -type f -ls`

## Security Relevance

Privilege auditing helps security analysts understand which users and groups have administrative access and how elevated privileges are configured.

Reviewing SUID binaries is also important because improperly configured or vulnerable SUID programs may provide a path to elevated privileges.

## Evidence

Screenshots documenting the investigation are stored in the `screenshots/` directory.

## Ethical Scope

This investigation was performed locally on a controlled Kali Linux system for cybersecurity education.

No unauthorized systems were accessed or tested.

All commands were used only for defensive security auditing.

## Learning Outcomes

Through this investigation, I practiced:

- Linux privilege auditing
- Sudo configuration analysis
- Group membership analysis
- SUID binary identification
- Root account status verification
- Security-focused documentation
- Linux command-line investigation

## Conclusion

This Linux user and privilege security audit demonstrated how standard Linux commands can be used to review administrative privileges, sudo configuration, privileged groups, and SUID binaries.

The investigation provides a basic foundation for identifying privilege-related security risks on Linux endpoints.
