# 03 — Linux Web Service Deployment

Hands-on Ubuntu Server lab focused on publishing, securing, and validating a web service in a cloud environment.

This activity introduced the process of taking a Linux server from a basic system to a publicly accessible web service using SSH, Nginx, UFW, HTTP, and browser/terminal validation.

---

## Objective

The objective of this lab was to:

- connect to a Linux cloud server remotely
- install and configure a web server
- publish web content
- configure firewall rules
- validate the service locally
- validate the service remotely
- document the technical implementation and evidence

---

## Environment

- **Operating System:** Ubuntu Server
- **Environment:** Cloud VPS
- **Remote Administration:** SSH
- **Web Server:** Nginx
- **Firewall:** UFW
- **Protocol:** HTTP
- **Web Port:** `80/tcp`
- **SSH Port:** `22/tcp`
- **Web Directory:** `/var/www/html`
- **Documentation:** GitHub

---

## Architecture

The basic publication flow was:

~~~text
Client / Browser
       |
       v
      HTTP
       |
       v
   Port 80
       |
       v
      UFW
       |
       v
     Nginx
       |
       v
  Web Content
~~~

Remote administration was handled separately:

~~~text
Administrator
      |
      v
     SSH
      |
      v
   Port 22
      |
      v
      UFW
      |
      v
   OpenSSH
      |
      v
 Ubuntu Server
~~~

---

## Remote Administration

The server was accessed remotely using SSH.

Example:

~~~bash
ssh user@SERVER_IP
~~~

SSH provided secure command-line access to the Ubuntu Server environment.

The lab also reinforced the importance of keeping administrative access separate from public web traffic.

---

## Installing Nginx

Nginx was installed and used as the web server.

Example package installation:

~~~bash
sudo apt update
sudo apt install nginx
~~~

The service status could then be checked with:

~~~bash
systemctl status nginx
~~~

This verified whether the web server was running correctly.

---

## Firewall Configuration

UFW was used to control incoming network traffic.

Before enabling the firewall, SSH access needed to remain available to avoid losing remote access to the server.

Example:

~~~bash
sudo ufw allow OpenSSH
sudo ufw allow 80/tcp
sudo ufw enable
~~~

Firewall status could be reviewed with:

~~~bash
sudo ufw status verbose
~~~

The goal was to expose only the network services required by the environment.

---

## Publishing the Web Service

Web content was published through the Nginx web directory:

~~~text
/var/www/html
~~~

The initial activity used a simple web page to verify that the server, firewall, and web-server configuration were working correctly.

This provided a simple way to validate the infrastructure before introducing more complex applications.

---

## Local Validation

The service was tested from the Linux server itself.

Example:

~~~bash
curl http://localhost
~~~

A successful response confirmed that:

- Nginx was running
- the local web service was responding
- the web content was being served correctly

---

## Remote Validation

The service was also tested using the server's public IP address.

Example:

~~~bash
curl http://SERVER_PUBLIC_IP
~~~

The web page was then tested from an external browser.

Example:

~~~text
http://SERVER_PUBLIC_IP
~~~

This confirmed that the complete network path was working:

~~~text
Internet
   ↓
Public IP
   ↓
Firewall
   ↓
Nginx
   ↓
Web Content
~~~

---

## Troubleshooting Approach

The activity introduced a basic troubleshooting sequence for web-service problems.

~~~text
Can I reach the server?
        ↓
Is SSH working?
        ↓
Is Nginx running?
        ↓
Is the firewall allowing traffic?
        ↓
Is the content in the correct directory?
        ↓
Does curl work locally?
        ↓
Does the service work remotely?
~~~

Useful commands include:

~~~bash
systemctl status nginx
sudo ufw status verbose
curl http://localhost
ip a
ss -tulpn
~~~

This approach helps isolate whether a problem is related to:

- the server
- the service
- the firewall
- networking
- web content
- remote connectivity

---

## Security Considerations

The lab introduced several basic Linux server security practices:

- Use SSH for remote administration
- Avoid unnecessary open ports
- Configure UFW before exposing services
- Keep administrative and public services separate
- Use a non-root user with `sudo` where appropriate
- Avoid publishing passwords, SSH keys, tokens, or credentials
- Validate firewall rules after configuration
- Review screenshots and documentation before publishing evidence

---

## Evidence

The project documentation includes evidence showing areas such as:

- SSH access
- Nginx service status
- firewall configuration
- web-content publication
- local validation
- public validation
- browser access

The objective of the evidence is to demonstrate the actual configuration and validation process rather than only describe the project.

---

## Practical Extension

The Linux web-server concepts practiced in this activity were later extended into a more complete web application environment.

I later used similar Linux administration skills to deploy and maintain my personal IT portfolio on a cloud VPS using:

- Ubuntu Server
- Nginx
- PHP
- MariaDB
- WordPress
- SSH
- UFW

That environment expanded the original exercise from a basic web-service deployment into a real application stack that I continue to use.

---

## Technologies & Tools

| Area | Technology |
|---|---|
| Operating System | Ubuntu Server |
| Remote Administration | SSH |
| Web Server | Nginx |
| Firewall | UFW |
| Protocol | HTTP |
| Service Management | systemctl |
| Validation | curl, browser testing |
| Networking | TCP/IP, ports |
| Documentation | GitHub, Markdown |

---

## Skills Demonstrated

- Ubuntu Server administration
- SSH remote access
- Nginx installation and validation
- firewall configuration
- UFW
- HTTP
- TCP/IP ports
- Linux service management
- `systemctl`
- `curl`
- basic web deployment
- connectivity troubleshooting
- technical documentation

---

## Key Takeaway

This lab demonstrated the complete basic workflow required to publish a service from a Linux cloud server:

~~~text
Prepare Server
      ↓
Connect with SSH
      ↓
Install Service
      ↓
Configure Firewall
      ↓
Publish Content
      ↓
Validate Locally
      ↓
Validate Remotely
      ↓
Document Evidence
~~~

It also provided the foundation for later work with more complete Linux web environments, including WordPress, PHP, MariaDB, and production-style VPS administration.
