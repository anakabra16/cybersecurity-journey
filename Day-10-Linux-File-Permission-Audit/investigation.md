# Linux File Permission Audit — Investigation Notes

## 1. Directory Permissions

### Command

```bash
ls -la

### Investigation

The command was used to review files and directories along with their permission settings.

### Security Relevance

Permission information helps identify which users and groups can read, write, or execute files.

### Evidence

![Directory Permissions](./screenshots/01-directory-permissions.png)

---

## 2. Home Directory Permissions

### Command

```bash
ls -ld ~

### Investigation

The home directory permissions were reviewed.

### Security Relevance

Reviewing home directory permissions helps determine whether access is appropriately restricted.

### Evidence

![Home Permissions](./screenshots/02-home-permissions.png)

---

## 3. World-Writable Directories

### Command

```bash
find ~ -type d -perm -0002 2>/dev/null

### Investigation

The command searched the user's home directory for directories writable by other users.

### Security Relevance

World-writable directories may allow unauthorized modification and should be reviewed to determine whether the permissions are intentional.

### Evidence

![World Writable Directories](./screenshots/03-world-writable-directories.png)

## Conclusion

This audit demonstarted basic linux permission  analysis and highlighted the importance of renewing file and directory access controls
