# Apache Port 5003 Fix – KodeKloud Task

###  Objective
Ensure Apache (httpd) service is running on **port 5003** on all three app servers in the Stratos DC.

---

###  Steps Performed

1. **Logged into each App Server**
   - stapp01 → tony / Ir0nM@n  
   - stapp02 → steve / Am3ric@  
   - stapp03 → banner / BigGr33n  

2. **Checked Apache status**
   ```bash
   sudo systemctl status httpd

3.Found port conflict (sendmail on 5003)

sudo ss -tuln | grep 5003

4.Stopped conflicting service

sudo systemctl stop sendmail
sudo systemctl disable sendmail

5.Updated Apache configuration

sudo vi /etc/httpd/conf/httpd.conf

Ensured Listen 5003

Added ServerName localhost


6.Restarted Apache

sudo systemctl restart httpd
sudo systemctl status httpd

7.Verified service

sudo ss -tuln | grep 5003


✅ Apache running successfully on port 5003 on all app servers.

🧾 Verification Output (Example)
Active: active (running)
tcp   LISTEN  0  128  0.0.0.0:5003  0.0.0.0:*
