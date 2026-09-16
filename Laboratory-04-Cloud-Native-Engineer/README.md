# Laboratory 04 – The Cloud-Native Engineer

## Mission Overview

  Congratulations! After successfully guiding our clients through multi-cloud evaluations, you have been 
promoted to the Cloud-Native Engineering Team at CloudNova Technologies. 
Modern cloud computing is no longer just about renting Virtual Machines (VMs) from AWS or Azure. Today's 
enterprise applications are built using lightweight, portable, and lightning-fast technologies called Containers. 
Your new mission is to understand the shift from traditional virtualization to containerization. 
Using the KillerCoda Playground, you will step into the shoes of a Cloud-Native Engineer. You will research the 
differences between VMs and containers, execute your very first Docker commands, and deploy a live, 
containerized web server in seconds. 
Remember: A traditional system administrator manages servers, but a cloud-native engineer manages 
the services running on them. 

## Objectives

 Differentiate between traditional Virtual Machines (VMs) and Containers. 
 Access a Docker-enabled cloud environment using KillerCoda. 
 Execute fundamental Docker CLI (Command Line Interface) commands. 
 Pull, run, manage, and terminate a containerized application (Nginx). 
 Create professional technical documentation of container operations using Markdown. 
 Continue developing a well-organized GitHub Cloud Computing Portfolio. 

## Docker Commands Executed

### `docker --version`

```bash
docker --version
```
### What does this command do
Displays the installed Docker version and confirms that Docker is available.

```bash
docker info
```
### What does this command do
Displays detailed information about the Docker environment and its current status.

```bash
docker pull nginx
```
### What does this command do
Downloads the official Nginx image from Docker Hub.

```bash
docker run -d -p 8080:80 --name nginx-server nginx
```
### What does this command do
Creates and runs an Nginx container in the background while mapping port 8080 on the host to port 80 inside the container.

```bash
docker ps
```
### What does this command do
Lists the Docker containers that are currently running.

```bash
curl http://localhost:8080
```
### What does this command do
Sends an HTTP request to the Nginx web server and displays its response in the terminal.

```bash
docker stop nginx-server
```
### What does this command do
Stops the running Nginx container named nginx-server.

```bash
docker rm nginx-server
```
### What does this command do
Removes the stopped nginx-server container from the Docker environment.

```bash
docker ps -a
```
### What does this command do
Lists all Docker containers, including running and stopped containers.

---

## Skills Learned

Through this activity, I learned how to use basic Docker commands in an Ubuntu environment. I learned how to pull an image from Docker Hub, create and run a container, and use port mapping to access a web server. I also learned how to check the status of a container, stop it, and remove it using the Docker CLI. Most importantly, I gained a better understanding of how containers can make application deployment faster and more resource-efficient compared with traditional virtual machines.

## Challenges Encountered

One of the challenges I encountered was understanding how port mapping works when running the Nginx container. At first, the -p 8080:80 option was confusing, but I learned that port 8080 on the host is connected to port 80 inside the container. I also had to understand why the Nginx container no longer appeared when I used docker ps after stopping it. After observing the results directly in the terminal, I became more comfortable with the basic Docker commands and the container lifecycle.




