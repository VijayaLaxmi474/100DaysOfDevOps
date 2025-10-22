#  Day 03 – Passwordless SSH Setup (thor → App Servers)

###  Objective
Configure **passwordless SSH authentication** from the **Jump Host (thor)** to all **Application Servers** (`stapp01`, `stapp02`, and `stapp03`) through their respective sudo users (`tony`, `steve`, `banner`).  
This setup ensures automation scripts can execute securely across servers without manual password input.

---

## nvironment Details

| Server Role | Hostname | IP Address | SSH User | Password |
|--------------|-----------|-------------|-----------|-----------|
| Jump Host | jump_host.stratos.xfusioncorp.com | Dynamic | thor | `mjolnir123` |
| App Server 1 | stapp01.stratos.xfusioncorp.com | 172.16.238.10 | tony | `Ir0nM@n` |
| App Server 2 | stapp02.stratos.xfusioncorp.com | 172.16.238.11 | steve | `Am3ric@` |
| App Server 3 | stapp03.stratos.xfusioncorp.com | 172.16.238.12 | banner | `BigGr33n` |

---

## mplementation Steps

### Step 1 – Connect to Jump Host
```bash
ssh thor@jump_host.stratos.xfusioncorp.com
# password: mjolnir123
Step 2 – Generate SSH Key Pair
ssh-keygen -t rsa


Press Enter for default file location /home/thor/.ssh/id_rsa

Leave passphrase empty for passwordless automation

Step 3 – Copy Public Key to App Servers

App Server 1

ssh-copy-id -i ~/.ssh/id_rsa.pub tony@stapp01
# password: Ir0nM@n


App Server 2

ssh-copy-id -i ~/.ssh/id_rsa.pub steve@stapp02
# password: Am3ric@


App Server 3

ssh-copy-id -i ~/.ssh/id_rsa.pub banner@stapp03
# password: BigGr33n

Step 4 – Verify Passwordless Connections
ssh tony@stapp01
ssh steve@stapp02
ssh banner@stapp03


All should connect without asking for passwords.

