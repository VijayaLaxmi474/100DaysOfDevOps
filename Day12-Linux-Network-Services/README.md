ask: Configure Apache Web Service on Port 8082

Objective:
To configure the Apache (httpd) web service to run on port 8082 and make it accessible from the jump host.

🪜 Steps Followed

Start the httpd service

sudo systemctl start httpd


Check if the service is running on port 8082

sudo netstat -tulnp | grep 8082


Troubleshoot connection issue

When testing with curl from the jump host:

curl http://stapp01:8082


It returned:
curl: (7) Failed to connect to stapp01 port 8082: No route to host

Check firewall rules using iptables

sudo iptables -L -n


Found that port 8082 was not allowed.

Allow port 8082 in iptables

sudo iptables -I INPUT -p tcp --dport 8082 -j ACCEPT


Save iptables rules

sudo service iptables save


Verify connection from jump host

curl http://stapp01:8082


 Web service accessible successfully.

Key Learnings

Managing Apache service on a non-default port.

Understanding Linux firewall (iptables).

Troubleshooting “No route to host” errors.

Network connectivity verification using curl.

Commands Summary
sudo systemctl start httpd
sudo netstat -tulnp | grep 8082
sudo iptables -I INPUT -p tcp --dport 8082 -j ACCEPT
sudo service iptables save
curl http://stapp01:8082
