# Docker Compose Guide

## Overview

In this activity, I learned how to use Docker Compose to run Nextcloud and MariaDB together. Instead of setting up each container separately, I used a `docker-compose.yml` file to put their configurations in one place and make them easier to manage.

## What Does the `services:` Block Do?

The `services:` block lists the containers needed for the application. In my configuration, the `database` service runs MariaDB, while the `app` service runs Nextcloud. Each service has its own settings, including the Docker image, environment variables, and port configuration.

## How Does Nextcloud Find the Database?

I used `MYSQL_HOST=database` to tell Nextcloud where to find the database. The word `database` matches the service name in my Compose file, so Nextcloud can use it to connect to MariaDB through Docker Compose's network.

## Difference Between `docker run` and `docker-compose up -d`

The `docker run` command is useful when I want to start an individual container by entering its settings directly in the terminal. On the other hand, `docker-compose up -d` uses a YAML file to start multiple related services together in the background. This makes Docker Compose more convenient when an application, like Nextcloud, needs a separate database to work properly.

## What I Learned

Through this activity, I understood how Docker Compose helps organize and manage multiple containers. I also learned how Nextcloud connects to MariaDB and how using a configuration file can make deploying an application easier.
