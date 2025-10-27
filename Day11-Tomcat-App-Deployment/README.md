# Apache Tomcat Application Deployment

This project demonstrates how to install and configure an Apache Tomcat server on a Linux environment, deploy a Java web application (`ROOT.war`), and run it on a custom port.

## Steps Performed
1. Installed Tomcat using `yum`
2. Configured Tomcat to run on port `5002`
3. Deployed `ROOT.war` into `/usr/share/tomcat/webapps/`
4. Verified successful deployment using `curl http://stapp01:5002`

## Technologies Used
- Apache Tomcat
- Java WAR Deployment
- Linux (CentOS)
- SCP & SSH
- Systemctl service management

## Verification
```bash
curl http://stapp01:5002
