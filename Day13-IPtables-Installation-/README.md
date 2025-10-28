# 🔥 Securing Apache Port with iptables

## 🧩 Project Overview
This project implements a firewall configuration using `iptables` to restrict Apache port access (8088) across multiple app servers.  
Only the Load Balancer host is allowed to connect, while all other incoming connections are blocked.

---

## ⚙️ Steps Implemented

1. **Installed iptables and dependencies**
   ```bash
   yum install iptables-services -y
Allowed LBR access and blocked all others

iptables -A INPUT -p tcp -s 172.16.238.14 --dport 8088 -j ACCEPT
iptables -A INPUT -p tcp --dport 8088 -j DROP


Saved and enabled rules for persistence

service iptables save
systemctl enable iptables
systemctl start iptables


Verified

iptables -L -n
cat /etc/sysconfig/iptables

✅ Expected Output
ACCEPT     tcp  --  172.16.238.14        0.0.0.0/0            tcp dpt:8088
DROP       tcp  --  0.0.0.0/0            0.0.0.0/0            tcp dpt:8088

📘 Key Learnings

iptables basics and rule order importance

How to make rules persistent using iptables-services

Importance of limiting access to application ports for better security

💻 Tools Used

CentOS / RHEL

iptables

systemctl
