# Day 1: Linux User Setup with Non-Interactive Shell

**Task:** Create a user named `je` with a non-interactive shell on App Server 1.

---

## Steps I Followed

```bash
# Connect to App Server 1
ssh tony@stapp01
# Password: Ir0nM@n

# Create user with non-interactive shell
sudo useradd -s /sbin/nologin je

# Verify
grep je /etc/passwd

# Exit
exit

