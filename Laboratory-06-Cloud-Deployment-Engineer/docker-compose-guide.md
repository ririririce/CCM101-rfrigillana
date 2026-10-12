# Docker Compose Guide

## Overview

Docker Compose makes it easier to run multiple containers that need to work together. In this laboratory, I used a `docker-compose.yml` file to configure Nextcloud and MariaDB so they can work as a private cloud storage system.

## What Does the `services:` Block Do?

The `services:` block defines the containers that Docker Compose needs to run. In my configuration, there are two services: `database`, which uses MariaDB to store application information, and `app`, which runs Nextcloud. Each service has its own settings, such as the image, environment variables, and port configuration.

## How Does Nextcloud Find the Database?

Nextcloud finds the database through the `MYSQL_HOST=database` environment variable in the Compose file. The name `database` matches the database service defined under `services:`. Docker Compose provides network communication between the services, allowing Nextcloud to connect to MariaDB using that service name.

## Difference Between `docker run` and `docker-compose up -d`

The `docker run` command is commonly used to create and start an individual container by specifying its settings directly in the terminal. In comparison, `docker-compose up -d` uses a YAML configuration file to start and manage multiple related services together in the background. This makes Docker Compose more convenient for applications like Nextcloud that depend on a separate database container.

## Conclusion

Through this activity, I learned how Docker Compose organizes multiple containers in one configuration file. It also helped me understand how Nextcloud and MariaDB communicate and how Infrastructure as Code can make deployments easier to manage.
