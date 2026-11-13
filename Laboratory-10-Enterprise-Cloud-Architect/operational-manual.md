#  CloudNova – Operational Manual

##  1. Introduction

This manual serves as a guide for setting up, running, securing, and maintaining the CloudNova system.

CloudNova is a web application hosted on Ubuntu Server inside Oracle VirtualBox. It uses Docker to run two connected services: WordPress and MariaDB.

This guide covers the basic commands and procedures needed to manage the server, monitor the application, maintain security, and perform database backups. It also includes instructions for restoring backups and troubleshooting common issues.

##  2. System Requirements

Before running CloudNova, make sure that the following software and components are available.

###  Host Machine

- Windows 11
- Oracle VirtualBox
- SSH client
- Web browser
- Internet connection

###  Virtual Machine

- Ubuntu Server 26.04.1 LTS
- 35 GB dynamically allocated virtual disk
- Docker Engine
- Docker Compose
- UFW Firewall
- OpenSSH Server

###  Application Components

- WordPress
- MariaDB 11.4
- Docker network
- Docker storage volumes

##  3. Server and Network Setup

### 3.1 Virtual Machine Information

CloudNova runs on an Ubuntu Server virtual machine created and managed through Oracle VirtualBox.

The following table shows the main virtual machine configuration:

| Configuration | Value |
|---|---|
| Server Name | `cloudnova-server` |
| Linux User | `cloudnova` |
| Operating System | Ubuntu Server 26.04.1 LTS |
| Virtualization Software | Oracle VirtualBox |
| Virtual Disk | 35 GB |

### 3.2 Network Configuration

The server uses two network interfaces to handle internet access and communication with the Windows host machine.

| Interface | IP Address | Purpose |
|---|---|---|
| `enp0s3` | `10.0.2.15` | Provides internet access |
| `enp0s8` | `192.168.56.103` | Connects the laptop to the server |

The Windows laptop uses `192.168.56.1` as its Host-only network address.

### 3.3 Connecting to the Server

To access Ubuntu Server remotely, open Windows PowerShell and enter the following command:

```powershell
ssh -i "$env:USERPROFILE\.ssh\cloudnova_ed25519" cloudnova@192.168.56.103
```

If prompted, enter the passphrase associated with your SSH key.

Once connected, you can execute commands and manage the server directly from PowerShell without opening the Ubuntu Server terminal in VirtualBox.

To access the WordPress website, open your preferred web browser and visit:

```text
http://192.168.56.103:8080
```

##  4. Running the Docker Application

CloudNova uses Docker and Docker Compose to run WordPress and MariaDB in separate containers. This setup makes it easier to manage each service while allowing them to communicate through a shared Docker network.

### 4.1 Checking Docker Installation

To check whether Docker Engine is installed, run:

```bash
sudo docker --version
```

To check the installed Docker Compose version, run:

```bash
sudo docker compose version
```

Both commands should display their respective version information.

### 4.2 Project Location

The CloudNova project files are stored on the Ubuntu Server in the following directory:

```text
/opt/cloudnova/
```

The deployed Docker configuration file is named `compose.yaml`, while the version included in the GitHub repository is named `docker-compose.yml`.

### 4.3 Application Containers

CloudNova consists of two main containers that work together to run the website.

**WordPress**

- Container name: `cloudnova-wordpress`
- Image: `wordpress:latest`
- Website address: `192.168.56.103:8080`
- Storage: `wordpress_data`

WordPress handles the website and allows users to manage its content through the web interface.

**MariaDB**

- Container name: `cloudnova-database`
- Image: `mariadb:11.4`
- Database settings: Stored in `.env`
- Storage: `mariadb_data`
- Access: Internal Docker network only

MariaDB stores the information used by WordPress, including website content and other application data.

### 4.4 Starting the Application

To start CloudNova, first connect to Ubuntu Server and navigate to the project directory:

```bash
cd /opt/cloudnova
```

Then run:

```bash
sudo docker compose up -d
```

This command starts the configured containers in the background.

To check whether the containers are running, use:

```bash
sudo docker ps
```

You can also check the status of the application services using:

```bash
sudo docker compose ps
```

### 4.5 Stopping and Restarting the Application

There may be times when you need to stop or restart the application for maintenance or troubleshooting.

**Stop the application:**

```bash
cd /opt/cloudnova
sudo docker compose stop
```

**Start the stopped containers again:**

```bash
sudo docker compose start
```

**Restart the containers:**

```bash
sudo docker compose restart
```

**Remove the containers and network without deleting stored data:**

```bash
sudo docker compose down
```

<text color="danger" weight="semibold" size="sm"> Important:</text>

Avoid using `docker compose down -v` unless you intentionally want to delete the Docker volumes containing the application's stored data. Removing these volumes can result in the loss of WordPress files and database information.

### 4.6 Checking Application Logs

Logs are useful when checking whether the application is working properly or investigating errors.

**View WordPress logs:**

```bash
sudo docker logs cloudnova-wordpress
```

**View MariaDB logs:**

```bash
sudo docker logs cloudnova-database
```

**View logs from both services continuously:**

```bash
sudo docker compose logs -f
```

Press `Ctrl + C` to stop viewing the live logs.

## 💾 5. Data Storage

CloudNova uses Docker volumes to preserve important website and database files. This allows stored information to remain available even when containers are stopped, restarted, or recreated.

The following volumes are configured:

| Volume | Storage Location | Purpose |
|---|---|---|
| `wordpress_data` | `/var/www/html` | Stores WordPress files |
| `mariadb_data` | `/var/lib/mysql` | Stores database files |

To view the available Docker volumes, run:

```bash
sudo docker volume ls
```

To check the details of the MariaDB volume, use:

```bash
sudo docker volume inspect mariadb_data
```

These volumes help prevent data loss during normal container operations. However, they should not be treated as a replacement for separate database backups. Keeping additional backup copies is still important in case of unexpected problems or data corruption.

##  6. Security Configuration

Security is an important part of maintaining CloudNova. Several configurations were applied to control network access, protect login credentials, and prevent unnecessary exposure of application services.

### 6.1 UFW Firewall

The Ubuntu firewall is configured to block incoming connections by default while allowing outgoing connections.

To apply the default firewall policies, run:

```bash
sudo ufw default deny incoming
sudo ufw default allow outgoing
```

To allow SSH connections only from the Host-only network, use:

```bash
sudo ufw allow from 192.168.56.0/24 to any port 22 proto tcp
```

After configuring the rules, enable the firewall:

```bash
sudo ufw enable
```

To review the current firewall configuration, run:

```bash
sudo ufw status verbose
```

The WordPress port is managed separately through Docker firewall rules. This is necessary because Docker-published ports can bypass some of the normal UFW filtering rules.

### 6.2 SSH Security

SSH is configured to use public-key authentication instead of password-based login. This provides a more controlled way to access the Ubuntu Server remotely.

The following security settings are included:

```text
PermitRootLogin no
PubkeyAuthentication yes
PasswordAuthentication no
KbdInteractiveAuthentication no
MaxAuthTries 3
X11Forwarding no
AllowUsers cloudnova
```

The SSH security configuration is stored in:

```text
/etc/ssh/sshd_config.d/99-security.conf
```

Before applying changes, check whether the SSH configuration contains any errors:

```bash
sudo sshd -t
```

To view the active SSH settings, run:

```bash
sudo sshd -T
```

After making changes to the configuration, reload the SSH service:

```bash
sudo systemctl reload ssh
```

<text color="danger" weight="semibold" size="sm"> Important:</text>

Keep your current SSH session open while testing new SSH settings. This gives you another way to access the server if the updated configuration prevents a new connection.

### 6.3 Docker Firewall Rules

Docker uses its own firewall rules to control access to published container ports. For CloudNova, additional rules are configured to limit access to the WordPress website.

The current firewall configuration:

1. Allows existing connections to continue.
2. Allows the Windows host (`192.168.56.1`) to access WordPress through the Host-only interface.
3. Blocks other traffic targeting the published WordPress port.

To view the current Docker firewall rules, run:

```bash
sudo iptables -S DOCKER-USER
```

The firewall script is located at:

```text
/usr/local/sbin/cloudnova-docker-firewall.sh
```

Its systemd service configuration is stored at:

```text
/etc/systemd/system/cloudnova-docker-firewall.service
```

To check whether the firewall service is running, use:

```bash
sudo systemctl status cloudnova-docker-firewall
```

### 6.4 Protecting Database Passwords

CloudNova stores its database credentials in a separate environment file instead of placing passwords directly in the application configuration.

The file is located at:

```text
/opt/cloudnova/.env
```

To check its current permissions, run:

```bash
sudo ls -l /opt/cloudnova/.env
```

**Important security reminders:**

- Never upload `.env` to GitHub.
- Avoid sharing database passwords publicly.
- Do not expose MariaDB port `3306` to the host network.
- Keep the `.env` file protected from unauthorized access.

WordPress communicates with MariaDB through the internal Docker network using the service name `database`.

## ⚙️ 7. Automatic Database Backup

CloudNova includes a custom Bash script that automatically creates backups of the MariaDB database. This helps maintain additional copies of important website information in case the original database encounters problems.

### 7.1 Backup Script

The backup script is stored on the Ubuntu Server at:

```text
/usr/local/sbin/cloudnova-db-backup.sh
```

The corresponding script included in the GitHub repository is named:

```text
automation-script.sh
```

The script handles the following tasks:

1. Reads the database settings from the `.env` file.
2. Checks whether the MariaDB container is running.
3. Creates a backup of the database.
4. Compresses the backup using Gzip.
5. Checks whether the generated backup file is valid.
6. Saves the backup using a filename containing the date and time.
7. Removes backup files that are more than seven days old.

This process helps keep backups organized and prevents older backup files from taking up unnecessary storage space.

### 7.2 Backup Location

All generated database backups are stored in:

```text
/opt/cloudnova/backups/
```

To view the available backup files and their sizes, run:

```bash
sudo ls -lh /opt/cloudnova/backups/
```

### 7.3 Creating a Manual Backup

Although backups are scheduled automatically, you can also run the script manually whenever needed.

Execute the following command:

```bash
sudo /usr/local/sbin/cloudnova-db-backup.sh
```

If the backup is successful, the script displays a confirmation similar to:

```text
SUCCESS: Database backup created.
File: /opt/cloudnova/backups/...
Size: ...
```

The generated file will be saved in the configured backup directory.

### 7.4 Checking Backup Files

After creating a backup, it is important to check whether the compressed file is valid.

Run:

```bash
sudo bash -c 'gzip -t "$(ls -t /opt/cloudnova/backups/*.sql.gz | head -n 1)" && echo "Backup archive is valid."'
```

If the command displays:

```text
Backup archive is valid.
```

It means the compressed backup passed the Gzip integrity check.

### 7.5 Automatic Backup Schedule

CloudNova is configured to create database backups every day at 2:00 AM UTC, which is equivalent to 10:00 AM Philippine Time.

The schedule is managed through the root user's Cron configuration.

To open the Cron configuration, run:

```bash
sudo crontab -e
```

The following entry is used to schedule the daily backup:

```cron
0 2 * * * /usr/local/sbin/cloudnova-db-backup.sh >> /var/log/cloudnova-backup.log 2>&1
```

This command automatically runs the backup script every day at the configured time and records its output in the backup log.

### 7.6 Checking the Scheduled Task

To display the currently configured Cron tasks, run:

```bash
sudo crontab -l
```

To check whether the Cron service is running, use:

```bash
sudo systemctl status cron
```

### 7.7 Checking Backup Logs

The backup script records its activities in the following log file:

```text
/var/log/cloudnova-backup.log
```

To view the complete log, run:

```bash
sudo cat /var/log/cloudnova-backup.log
```

To view only the latest 50 entries, use:

```bash
sudo tail -n 50 /var/log/cloudnova-backup.log
```

Checking the logs helps you determine whether scheduled backups are running successfully or encountering errors.

## ♻️ 8. Restoring a Database Backup

If the MariaDB database needs to be recovered, an existing compressed SQL backup can be used to restore its contents.

<text color="danger" weight="semibold" size="sm"> Warning:</text>

Restoring a backup can replace the current database contents. Before proceeding, create a separate backup of the current database so that its information can still be recovered if needed.

**Step 1: Load the database settings**

Navigate to the CloudNova project directory:

```bash
cd /opt/cloudnova
```

Load the environment variables from `.env`:

```bash
set -a
source .env
set +a
```

**Step 2: Specify the backup file**

Set the filename of the backup you want to restore:

```bash
BACKUP_FILE="/opt/cloudnova/backups/your_backup_filename.sql.gz"
```

Replace `your_backup_filename.sql.gz` with the actual name of the backup file.

**Step 3: Restore the database**

Run the following command:

```bash
sudo bash -c 'gunzip -c "$1" | docker exec -i -e MYSQL_PWD="$2" cloudnova-database mariadb -u root "$3"' _ "$BACKUP_FILE" "$DB_ROOT_PASSWORD" "$DB_NAME"
```

This command decompresses the selected backup and sends its SQL contents to the MariaDB container for restoration.

**Step 4: Check the MariaDB logs**

After the restoration process, check the database logs for any errors:

```bash
sudo docker logs --tail 50 cloudnova-database
```

## 🔧 9. Maintenance and Troubleshooting

Regularly checking the server and application helps identify problems before they affect the website.

The following commands can be used to monitor the system and troubleshoot common issues.

### 9.1 Check Running Containers

To see all containers, including those that are currently stopped, run:

```bash
sudo docker ps -a
```

### 9.2 Restart Docker

If Docker encounters a problem, you can restart its service using:

```bash
sudo systemctl restart docker
```

### 9.3 Check Available Disk Space

To see how much storage is available on the server, run:

```bash
df -h
```

### 9.4 Check Memory Usage

To check the server's current memory usage, use:

```bash
free -h
```

### 9.5 Check Network Settings

To view the server's network interfaces and IP addresses, run:

```bash
ip addr
```

To check the configured network routes, use:

```bash
ip route
```

### 9.6 Check Firewall Rules

To review the UFW firewall configuration, run:

```bash
sudo ufw status verbose
```

To inspect the Docker firewall rules, use:

```bash
sudo iptables -S DOCKER-USER
```

### 9.7 Check Docker Firewall Service

To check the status of the CloudNova Docker firewall service, run:

```bash
sudo systemctl status cloudnova-docker-firewall
```

### 9.8 Check Backup Logs

To review recent database backup activities, use:

```bash
sudo tail -n 50 /var/log/cloudnova-backup.log
```

### 9.9 Common Problems

The following table lists some issues you might encounter while using CloudNova, their possible causes, and suggested solutions.

| Problem | Possible Cause | Solution |
|---|---|---|
| WordPress cannot be accessed | Container is stopped or network is not working | Check the container status and network settings. |
| WordPress cannot connect to MariaDB | Database is not running or is not healthy | Check the MariaDB container status and logs. |
| SSH connection is denied | Incorrect SSH key or server configuration | Verify the SSH key and review the server's SSH settings. |
| Backup script fails | Database is unavailable or required settings are missing | Check MariaDB and review the `.env` file. |
| Server storage is full | Too many stored files or old backups | Check disk usage and review older backup files. |
| Website cannot be accessed from Windows | Incorrect firewall rules or Host-only network settings | Review the Docker firewall rules and network interfaces. |

## 📋 10. Important Maintenance Reminders

To keep CloudNova running properly and reduce the risk of data loss or security problems, remember the following:

- Keep database passwords private and secure.
- Never upload the `.env` file to GitHub.
- Keep MariaDB accessible only through the internal Docker network.
- Avoid disabling firewall rules without understanding their purpose.
- Check database backup files regularly.
- Keep another copy of important backups outside the virtual machine.
- Avoid deleting Docker volumes without checking their contents.
- Monitor the server's available disk space.
- Review application updates before applying them.

Following these reminders can help maintain the system and protect important application data.

##  11. Conclusion

This operational manual provides the instructions needed to manage and maintain the CloudNova system. It covers the server setup, Docker application, network configuration, security settings, data storage, backup automation, and troubleshooting procedures.

By following these instructions, the system can be managed more easily while keeping the website accessible, protecting server access, and maintaining copies of important database information.

CloudNova is not just about deploying a working website. It also involves making sure that the application remains manageable, its data is protected, and its services can be maintained when problems occur.

This manual serves as a reference for the regular operation and maintenance of the project.
