# Laboratory 08 – Cloud Security Engineer

## Mission Overview

  Congratulations! Your proactive approach to system monitoring has earned you a spot on the elite 
Cloud Security Team at CloudNova Technologies. 
  In the cloud, leaving a server unsecured for even a few minutes can lead to automated brute-force 
attacks and data breaches. Your mission today applies the security concepts you learned in Chapter 8. You will 
implement the principle of defense in depth by locking down a live server using a host-based firewall. 
  Using the KillerCoda Playground, you will step into the role of a Cloud Security Engineer. You will 
deploy a web application, audit the server's open ports, and configure the Uncomplicated Firewall (UFW) to block 
malicious traffic while allowing legitimate users to access the application. 
Remember: Security is not a product you buy; it is a continuous process you maintain.

## Objectives

- Understand the concept of the Attack Surface and the Principle of Least Privilege (PoLP).
- Perform a basic security audit of active network ports on a Linux server.
- Perform a basic security audit of active network ports on a Linux server.
- Implement granular port management to selectively allow SSH and HTTP traffic.
- Document firewall rules and security best practices using Markdown.
- Continue expanding your professional GitHub Cloud Computing Portfolio.

## Commands Executed

**Deploy the Nginx container**

```bash
docker run -d --name secure-web-app -p 8080:80 nginx
```

**Test the web application**

```bash
curl http://localhost:8080
docker ps
```

**Configure the firewall**

```bash
sudo ufw allow ssh
sudo ufw default deny incoming
sudo ufw default allow outgoing
sudo ufw enable
```

**Allow port 8080 and verify the rules**

```bash
sudo ufw allow 8080/tcp
sudo ufw status verbose
sudo ufw status numbered
curl http://localhost:8080
```

## Skills Learned

Through this activity, I learned how to use Docker to run a web server and secure it with UFW. I also learned why it is important to allow only the ports needed by the application instead of leaving unnecessary connections open. Testing the application with `curl` and checking the firewall rules helped me understand how to verify that the server was running and properly configured. Overall, this activity gave me a better understanding of basic server security and how small configuration changes can help protect a system.
