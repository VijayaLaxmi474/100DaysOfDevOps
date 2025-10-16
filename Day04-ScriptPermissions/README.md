# Day 04 - Grant Script Execute Permissions (KodeKloud Task)

## 🧠 Task Objective
Ensure that the backup automation script `/tmp/xfusioncorp.sh` is executable by all users on App Server 1.

## ⚙️ Steps Performed
1. Connected to App Server 1 via SSH:
   ```bash
   ssh tony@stapp01
Verified file permissions:

ls -l /tmp/xfusioncorp.sh


Granted executable permission to all users:

sudo chmod a+rx /tmp/xfusioncorp.sh


Verified changes:

ls -l /tmp/xfusioncorp.sh


Output:

-rwxr-xr-x 1 root root 40 Oct 16 02:01 /tmp/xfusioncorp.sh


Tested the script:

/tmp/xfusioncorp.sh

✅ Result

The script is now executable by all users (-rwxr-xr-x).

🧩 Commands Used

chmod → Change file permissions

ls -l → View file permissions

sudo → Execute command with root privileges

🧰 Tools Practiced

Linux File Permissions

Bash Basics

SSH Access
