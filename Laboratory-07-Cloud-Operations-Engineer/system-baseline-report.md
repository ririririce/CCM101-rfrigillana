# System Baseline Report

## Host System Resources

Before deploying the web server, I checked the current resources of my Ubuntu environment using Linux commands.

| Resource | Result |
|---|---|
| Total RAM | 1.9 GiB |
| Root Filesystem Storage Capacity | 19G |

## Importance of Checking Disk Space

Checking disk space before a massive traffic surge is important because the server needs enough storage for application logs, temporary files, and other data generated when more users access the website.

## Commands Used

- `free -h` – Displays the system's memory usage and available RAM.
- `df -h /` – Shows the total, used, and available storage of the root filesystem.
- `top` – Displays running processes and real-time CPU and memory usage.

