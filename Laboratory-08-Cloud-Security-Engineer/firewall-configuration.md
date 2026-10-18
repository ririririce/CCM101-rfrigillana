# Firewall Configuration

## Overview

In this activity, I used UFW (Uncomplicated Firewall) to secure my Ubuntu server. I allowed SSH so administrators could still access the server remotely, blocked incoming traffic by default, and allowed port 8080 so users could access my Nginx web application.

## 1. Allow SSH Access

```bash
sudo ufw allow ssh
```

I ran this command to allow SSH connections, which are needed to manage the server remotely.

## 2. Set the Default Firewall Policies

```bash
sudo ufw default deny incoming
sudo ufw default allow outgoing
```

I used these commands to block incoming connections by default while still allowing the server to connect to other services. This helps limit unwanted access to the server.

## 3. Allow Port 8080

```bash
sudo ufw allow 8080/tcp
```

I added this rule to allow TCP traffic through port 8080 so users could access the Nginx web application running on my server.

## 4. Enable and Check the Firewall

```bash
sudo ufw enable
sudo ufw status verbose
```

I enabled UFW and checked its status to make sure the firewall was active and the default policies were properly applied.

## 5. Why SSH Must Be Allowed First

If I enabled UFW before allowing SSH, I could lose remote access to the server because incoming SSH connections might be blocked by the firewall.

