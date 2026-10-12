# Multi-Tier Architecture

## What is a Two-Tier Architecture?

A two-tier architecture is a system that has two main parts: the web/application tier and the database tier. For this laboratory, we will use Nextcloud as the web application and MariaDB as the database. They run in separate Docker containers and work together to make the private cloud storage system function properly.

## The Web/Application Tier

The web/application tier is the part that users interact with through their web browsers. In our setup, Nextcloud lets users access and manage their files. It also handles their requests and communicates with the database whenever information needs to be saved or retrieved.

## The Database Tier

The database tier is responsible for storing and managing information used by the application, such as user accounts and file details. In our setup, MariaDB stores the information that Nextcloud needs. This allows the application to retrieve the correct data whenever it is needed.

## Why Separate Them?

Keeping the web application and database in separate containers makes them easier to manage and troubleshoot. If we need to update one part, we can work on it separately instead of changing the entire setup. This also makes the system more flexible because each container can be maintained or scaled depending on its needs.
