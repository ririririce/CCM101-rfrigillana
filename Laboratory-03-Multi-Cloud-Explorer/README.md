# Linux Server Information

## 1. Operating System

### Command Used

```bash
cat /etc/os-release
```
What the command does:

The cat /etc/os-release command displays information about the Linux operating system by reading the /etc/os-release file. It shows details such as the distribution name, version, and release information.

<img width="1911" height="993" alt="image" src="https://github.com/user-attachments/assets/c80ebdec-8127-4f34-bf96-4f3fc0692aac" />


## 2. CPU Information

### Command Used

```bash
lscpu
```
What the command does:

The lscpu command displays detailed information about the system's CPU. It shows details such as the CPU architecture, processor model, number of CPUs, cores, threads, virtualization, cache, and other processor-related information.

<img width="1917" height="995" alt="image" src="https://github.com/user-attachments/assets/87fdeb1c-8079-40b7-81d4-54a37c56f18e" />


## 3. Memory

### Command Used

```bash
free -h
```
What the command does:

The free -h command displays information about the system's memory usage in a human-readable format. It shows the total, used, free, shared, cached, and available memory, as well as the swap memory.

<img width="1917" height="996" alt="image" src="https://github.com/user-attachments/assets/7c615580-95e6-4791-ad98-e79cba5f5ec4" />


## 4. Disk Space

### Command Used

```bash
df -h
```
What the command does:

The df -h command displays the disk space usage of the system's mounted filesystems in a human-readable format. It shows the total size, used space, available space, usage percentage, and mount point of each filesystem.

<img width="1914" height="994" alt="image" src="https://github.com/user-attachments/assets/7dd77d96-b490-48d7-b7d5-ab7b2c33d14e" />



---

If this Linux server were migrated to the cloud, it could be hosted as a virtual machine. Since the server is running Ubuntu Linux, it can be moved to a cloud service that supports Linux virtual machines.

| Cloud Provider | Service | How It Could Host the Linux Server |
|---|---|---|
| **AWS** | Amazon EC2 | Can be used to create a Linux virtual machine and run applications or services on it. |
| **Microsoft Azure** | Azure Virtual Machines | Can run Linux virtual machines, including Ubuntu, for applications and server workloads. |
| **Google Cloud** | Compute Engine | Can create a Linux virtual machine with customizable computing resources for running applications and services. |

### My Understanding

The Linux server I used in KillerCoda could be hosted on any of these three cloud platforms. **Amazon EC2, Azure Virtual Machines, and Compute Engine** all provide virtual machines that can run Linux. The main difference would be which cloud provider and features would be the best fit for the project's needs.
