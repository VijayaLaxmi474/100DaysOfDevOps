# 🔒 Day 4 — SELinux Configuration and Security Enhancement

### 🧠 Task Overview
Following a recent security audit, the **xFusionCorp Industries** security team decided to enhance application and server security by implementing **SELinux**.  
The task was performed on **App Server 1 (stapp01)** within the **Stratos Datacenter**.

### 🎯 Objective
- Install required SELinux packages  
- Permanently disable SELinux for the time being (no reboot required)  
- Ensure that after reboot, SELinux remains disabled  

---

### 🖥️ Server Details
| Detail | Value |
|--------|--------|
| Server Name | stapp01 |
| IP Address | 172.16.238.10 |
| Hostname | stapp01.stratos.xfusioncorp.com |
| User | tony |
| Password | Ir0nM@n |
| Purpose | Nautilus App 1 |

---

### ⚙️ Steps Performed

#### 1️⃣ SSH into App Server 1
```bash
ssh tony@stapp01
