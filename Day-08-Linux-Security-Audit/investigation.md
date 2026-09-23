# Linux Security Audit — Investigation Notes

## 1. Investigation Objective

The objective of this investigation was to perform a basic security audit of a Kali Linux system from a defensive cybersecurity perspective.

The investigation focused on user identity, group membership, local user and group configuration, SUID files, world-writable files, SSH configuration, and running services.

---

## 2. Current User Investigation

### Commands Used

```bash
whoami


paste this **next part**:

```markdown
```bash
id

### Observation

The current logged-in Linux user and associated user and group information were identified.

The `id` command was used to review the user's UID, GID, and group memberships.

### Security Relevance

User and group information is important during Linux security assessments because permissions and access to system resources are determined partly by account and group membership.

### Evidence

![Current User](./screenshots/01-current-user.png)

---

## 3. User Groups Investigation
### Command Used

```bash
id
```

### Investigation

The user's group memberships were reviewed to identify the groups associated with the current account.

### Observation

The command displayed the user's primary group and additional group memberships.

### Security Relevance

Membership in privileged groups can provide additional access to system resources. Analysts should review group membership when auditing Linux accounts and permissions.

### Evidence

![User Groups](./screenshots/02-user-groups.png)

---

## 4. Local User Account Investigation
