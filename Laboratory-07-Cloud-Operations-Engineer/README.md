# Laboratory 7 – The Cloud Operations Engineer

## Mission Overview

  Congratulations! Your ability to deploy multi-tier architectures has proven your technical capabilities. 
You have now been promoted to the Cloud Operations Team (often referred to in the industry as Site Reliability 
Engineering, or SRE) at CloudNova Technologies. 
  Deploying a cloud application is only the first step; keeping it running smoothly is the real challenge. 
When a server crashes or a web page takes ten seconds to load, you cannot simply guess what is wrong. You 
must rely on Observability and Monitoring to see inside your infrastructure. 
  Using the KillerCoda Playground, you will step into the role of a Cloud Operations Engineer. You will 
establish a performance baseline for your Linux server, deploy a containerized application, generate artificial web 
traffic, and hunt down performance metrics and system logs to prove the application is healthy. 
Remember: A developer hopes the application works; a Site Reliability Engineer uses metrics and logs to 
prove it.

## Objectives

- Utilize native Linux command-line tools to monitor host CPU, Memory, and Disk capacity.
- Deploy a web container and track its real-time performance using Docker metrics.
- Generate web traffic and extract application access logs for analysis.
- Translate raw performance data into a readable technical report using Markdown. 
- Continue expanding a professional GitHub Cloud Computing Portfolio. 

## Monitoring Commands Executed

| Command | Purpose |
|---|---|
| `free -h` | Checks RAM usage and available memory. |
| `df -h /` | Displays the root filesystem's total and available storage. |
| `top` | Monitors running processes and CPU activity. |
| `docker run -d -p 8080:80 --name client-website nginx` | Deploys the Nginx web server in the background. |
| `docker ps` | Checks the running Docker containers. |
| `curl http://localhost:8080` | Sends an HTTP request to the website. |
| `curl http://localhost:8080/hidden-admin-page` | Simulates a request to a nonexistent page. |
| `docker logs client-website` | Displays the container's application logs. |
| `docker stats` | Monitors the container's CPU, memory, and network usage. |

## Skills Learned

Through this activity, I learned how to check server resources, run a web server using Docker, and generate HTTP requests to test its response. I also practiced reading application logs to find errors and using `docker stats` to monitor resource usage. These tasks helped me understand how monitoring tools can make it easier to identify problems and keep a web application running properly.
