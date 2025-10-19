# 🚀 Day 6 - Automate Tasks Using Cron Jobs

## 🧩 Task Description
The Nautilus DevOps team wanted to automate recurring tasks using cron.  
This exercise focuses on setting up and verifying cron jobs on all application servers.

### Requirements:
1. Install `cronie` package
2. Start and enable `crond` service
3. Add a cron job for the **root user** to run every 5 minutes
2️⃣ Switch to Root
sudo su -

3️⃣ Install Cronie
yum install cronie -y

4️⃣ Start and Enable Cron Service
systemctl start crond
systemctl enable crond

5️⃣ Add Cron Job for Root
crontab -e
# Add this line:
*/5 * * * * echo hello > /tmp/cron_text

6️⃣ Verify
crontab -l
grep CRON /var/log/messages
cat /tmp/cron_text


✅ Expected Output:

hello

🧠 Learnings

Automate periodic tasks using cron

Manage system-wide scheduling via crond

Verify cron job execution using logs and file outputs

Useful for backups, cleanup, and monitoring in DevOps pipelines

🏁 Outcome

Successfully scheduled a Linux cron job that executes every 5 minutes.
This is a foundational skill for system automation and DevOps workflows.
