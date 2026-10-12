# The Cloud Deployment Engineer

## Mission Overview

  Congratulations! Your flawless work in deploying data storage solutions has earned you a spot on the 
Cloud Deployment Team at CloudNova Technologies. 
  Up until now, you have been deploying single containers (like a standalone web server or a storage 
bucket). However, real-world enterprise applications are rarely just one container. They are "multi-tier" systems 
that require a frontend web application communicating seamlessly with a backend database. Deploying these 
one by one manually is prone to error. 
  Enter Docker Compose. In this mission, you will transition from manual commands to Infrastructure 
as Code (IaC). Using a YAML configuration file, you will define a multi-container private cloud storage application 
(Nextcloud and MariaDB) and deploy the entire stack simultaneously with a single command! 
Remember: A junior engineer deploys servers by typing commands; a senior engineer deploys 
infrastructure by writing code.

## Objectives

- Explain the concept of a multi-tier application architecture..
- Understand the purpose and structure of a docker-compose.yml file.
- Use a Linux command-line text editor (nano) to create configuration files.
- Deploy a multi-container application (Nextcloud + Database) using Docker Compose.
- Document deployment procedures and Infrastructure as Code (IaC) principles using Markdown.
- Continue expanding your professional GitHub Cloud Computing Portfolio.

## Commands Executed

| Command | Purpose |
|---|---|
| `mkdir nextcloud-deployment` | Creates a folder for the project. |
| `cd nextcloud-deployment` | Opens the project folder in the terminal. |
| `nano docker-compose.yml` | Creates or edits the Compose file. |
| `cat docker-compose.yml` | Displays the contents of the Compose file. |
| `docker-compose up -d` | Starts the services in the background. |
| `docker-compose ps` | Checks whether the containers are running. |
| `docker-compose down` | Stops and removes the Compose containers and network. |

##  Tools Used

- 🐳 **Docker** — Runs applications in containers.
- ⚙️ **Docker Compose** — Helps run and manage multiple related containers.
- ☁️ **Nextcloud** — Provides the private cloud storage application.
- 🗄️ **MariaDB** — Manages the application's database.
- 🖥️ **KillerCoda Ubuntu Playground** — Provides the environment for running the commands.
- 📝 **Markdown** — Used to document the activity.

## Skills Learned

This activity helped me understand how different containers can work together to run an application. I learned how to organize their settings in a YAML file and how Nextcloud connects to MariaDB. I also had more practice using Linux commands and writing technical documentation in Markdown.

Overall, this laboratory helped me see how Docker Compose can make setting up and managing applications easier, especially when they need more than one container to work properly.
