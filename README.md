# Secure-Copy

## Copying Files from Server to Kali or Windows

---

### How SCP works

```
scp  SOURCE  DESTINATION
```
- **Remote path format:** `user@ip:/path/to/file`
- **Local path format:** `/home/kali/Desktop/` or `~/Desktop/`
- Always run on the **machine you're copying TO** (the destination)

---

### Server details from your session
- Server IP: `10.10.10.10`
- Server user: `leo_audit`
- Files location: `/home/leo_audit/subnets/`

---

### Option 1 — Copy to Kali

**Run this on Kali:**

```bash
# Single file
scp leo_audit@10.10.10.10:/home/leo_audit/subnets/results.txt ~/Desktop/

# Multiple files at once
scp leo_audit@10.10.10.10:/home/leo_audit/subnets/{results.txt,nmap_scan.txt} ~/Desktop/

# Entire directory
scp -r leo_audit@10.10.10.10:/home/leo_audit/subnets/ ~/Desktop/
```

---

### Option 2 — Copy to Windows

**Run this in PowerShell on Windows:**

```powershell
# Single file
scp leo_audit@10.10.10.10:/home/leo_audit/subnets/results.txt C:\Users\YourUser\Desktop\

# Multiple files
scp leo_audit@10.10.10.10:/home/leo_audit/subnets/{results.txt,nmap_scan.txt} C:\Users\YourUser\Desktop\

# Entire directory
scp -r leo_audit@10.10.10.10:/home/leo_audit/subnets/ C:\Users\YourUser\Desktop\
```

---

### Common mistakes to avoid

| Mistake | Wrong | Right |
|---|---|---|
| Running on server | `scp` on server | Run on Kali or Windows |
| Trailing space in path | `/subnets/results.txt ` | `/subnets/results.txt` |
| Wrong username | `mac_audit@...` | `leo_audit@...` |
| Backslash in path | `leo_audit\subnets` | `leo_audit/subnets` |
