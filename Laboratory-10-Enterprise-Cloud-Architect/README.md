#  Enterprise Cloud Architect

##  Project Overview

**CloudNova** is an enterprise cloud infrastructure project developed for CCM101 – Cloud Computing. The project focuses on building and managing a web application using virtualization and containerization technologies.

It uses Ubuntu Server as its main operating system and Docker to run two connected services: WordPress and MariaDB. WordPress serves as the website platform, while MariaDB handles the storage and management of website data.

Aside from deploying the application, the project also focuses on server security, network configuration, persistent storage, and automated database backups. These features help keep the application accessible, its data protected, and its services easier to manage.

##  Project Objectives

The main objectives of this project are to:

- Set up and configure a Linux server using Oracle VirtualBox.
- Establish network communication between the Windows host machine and the virtual server.
- Install and configure Docker Engine and Docker Compose.
- Deploy WordPress and MariaDB as interconnected services.
- Configure persistent storage to prevent data loss when containers restart.
- Improve server security through firewall rules and secure SSH access.
- Develop a Bash script to automate database backups.
- Schedule regular backups using Cron.
- Prepare documentation covering the system setup, operation, and maintenance.

##  System Architecture

CloudNova is built using several components that work together to provide a functional and secure web application.

The system consists of the following:

1. **Host Machine:** A Windows 11 laptop used to manage and access the Ubuntu Server.
2. **VirtualBox:** Provides the virtual environment where Ubuntu Server runs.
3. **Ubuntu Server:** Serves as the main operating system and host for Docker.
4. **Network Configuration:** NAT provides internet connectivity, while Host-only networking allows communication between the Windows laptop and the virtual machine.
5. **Firewall:** UFW and iptables are used to manage and control incoming network connections.
6. **Docker:** Runs the application's services inside separate containers.
7. **WordPress:** Handles the website and its content.
8. **MariaDB:** Stores and manages the website's database.
9. **Persistent Storage:** Docker volumes preserve WordPress files and database information even when containers are stopped or restarted.
10. **Backup Automation:** Bash and Cron work together to create scheduled database backups.

For a visual representation of how these components are connected, see the [architecture diagram](architecture-diagram.png).

##  Technologies Used

The following technologies and tools were used to develop and manage CloudNova:

| Component | Technology |
|---|---|
| Host Operating System | Windows 11 |
| Virtualization Software | Oracle VirtualBox |
| Server Operating System | Ubuntu Server 26.04.1 LTS |
| Container Platform | Docker Engine 29.9.2 |
| Container Management | Docker Compose 5.6.1 |
| Website Platform | WordPress |
| Database Management System | MariaDB 11.4 |
| Firewall | UFW and iptables |
| Automation | Bash and Cron |
| Remote Access | OpenSSH |
| SSH Authentication | ED25519 Key |

##  Network Configuration

The project uses two network interfaces to provide internet access and communication between the host machine and the virtual server.

| Interface | IP Address | Purpose |
|---|---|---|
| NAT (`enp0s3`) | `10.0.2.15/24` | Provides internet access to the virtual machine. |
| Host-only (`enp0s8`) | `192.168.56.103/24` | Allows communication between the laptop and server. |
| Windows Host-only Adapter | `192.168.56.1` | Connects the Windows host to the virtual machine. |
| WordPress | `192.168.56.103:8080` | Provides access to the website. |

** WordPress Website:**

`http://192.168.56.103:8080`

The website can be accessed through a web browser on the Windows host machine using the configured Host-only network address.

##  Docker Services

CloudNova uses Docker Compose to run and manage two containers that work together to support the website.

| Container | Image | Purpose |
|---|---|---|
| `cloudnova-wordpress` | `wordpress:latest` | Runs the WordPress website. |
| `cloudnova-database` | `mariadb:11.4` | Stores and manages website data. |

Both containers communicate through a dedicated Docker network called `cloudnova-network`. This allows WordPress to connect to the database without exposing the database directly to the host network.

** Persistent Storage**

Two Docker volumes are configured to keep important application data:

- `wordpress_data` – stores WordPress files and website content.
- `mariadb_data` – stores database files and records.

Using persistent volumes helps protect stored information when containers are stopped, restarted, or recreated.

##  Security Features

Security is an important part of CloudNova. Several configurations were applied to limit unnecessary access and protect the server and its data.

The following security measures were implemented:

- **UFW Firewall:** Enabled with a default policy that denies incoming connections unless they are explicitly allowed.
- **Outgoing Connections:** Allowed to support normal server communication and internet access.
- **SSH Access:** Restricted to connections from the Host-only network.
- **Password Authentication:** Disabled for SSH to prevent password-based remote logins.
- **Root Login:** Direct root access through SSH is disabled.
- **SSH Key Authentication:** ED25519 public-key authentication is used for secure remote access.
- **Docker Network Security:** Website access is restricted to the Windows host through the configured firewall rules.
- **Database Protection:** MariaDB is accessible only through the internal Docker network and is not directly exposed to the host network.
- **Environment Variables:** Database credentials are stored in a protected `.env` file, which is excluded from the GitHub repository.

These configurations help reduce unnecessary network exposure and provide better control over who can access the server and its services.

##  Backup Automation

To help prevent data loss, CloudNova includes a custom Bash script that automatically creates backups of the MariaDB database.

**Script:** `automation-script.sh`

**Backup Location:** `/opt/cloudnova/backups/`

**Backup Schedule:** Every day at 2:00 AM UTC (10:00 AM Philippine Time).

The backup script performs the following tasks:

- Creates a backup of the MariaDB database.
- Compresses the backup file using Gzip to reduce its storage size.
- Adds a date and time to each filename for easier identification.
- Checks the generated backup file to make sure it is valid.
- Automatically removes backups that are more than seven days old.
- Records backup activities and results in a log file.

Cron is used to run the script automatically based on the configured schedule. This reduces the need to create backups manually and helps maintain regular copies of the database.

##  GitHub Repository Structure

The project files are organized as follows:

```text
Laboratory-10-Enterprise-Cloud-Architect/
├── README.md
├── architecture-diagram.png
├── docker-compose.yml
├── automation-script.sh
├── operational-manual.md
└── final-reflection.md
```

Each file serves a specific purpose, from configuring the application to documenting the system and its maintenance procedures.

##  Basic Deployment Commands

The following commands can be used to manage the CloudNova application.

**1. Navigate to the project directory**

```bash
cd /opt/cloudnova
```

**2. Start the application**

```bash
sudo docker compose up -d
```

**3. Check running containers**

```bash
sudo docker ps
```

**4. View application logs**

```bash
sudo docker compose logs
```

**5. Access the WordPress website**

Open a browser and visit:

```text
http://192.168.56.103:8080
```

For more detailed instructions about the initial setup, security configuration, backup process, and system maintenance, refer to the [operational manual](operational-manual.md).

##  Project Deliverables

The following files contain the main outputs of the project:

- `architecture-diagram.png` – provides a visual overview of the server architecture and network connections.
- `docker-compose.yml` – contains the configuration for the WordPress and MariaDB containers.
- `automation-script.sh` – handles the automated creation and management of database backups.
- `operational-manual.md` – provides instructions for setting up, operating, and maintaining the system.
- `final-reflection.md` – presents the experiences, challenges, and lessons learned throughout the project.

##  Conclusion

CloudNova brings together different cloud computing concepts and technologies to build a working web application in a virtualized environment. Through this project, virtualization, Docker, networking, persistent storage, server security, and automation were put into practice.

Beyond simply deploying WordPress and MariaDB, the project also demonstrates the importance of protecting application data, controlling server access, and maintaining regular backups.

Overall, this project provided an opportunity to gain hands-on experience in setting up and managing a cloud-based environment while understanding how its different components work together.
