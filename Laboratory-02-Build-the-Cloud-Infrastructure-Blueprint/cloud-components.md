
## Compute Resources

The KillerCoda Linux environment uses an **Intel Xeon E312xx (Sandy Bridge, IBRS update)** processor with **1 CPU core**. The system also has approximately **1.9 GiB of RAM** available.

### Purpose

Compute resources provide the processing power and memory needed to run applications, execute commands, and perform tasks. The CPU handles instructions and calculations, while RAM temporarily holds the data and programs currently being used by the system.

### Importance in Cloud Computing

Compute resources are essential in cloud computing because they allow applications and workloads to run without requiring users to maintain physical servers themselves. Cloud providers can allocate and scale computing resources based on the needs of their users.

### Relation to the KillerCoda Environment

The CPU and RAM provided by KillerCoda allow the Ubuntu environment to execute Linux commands and run the tools needed for the laboratory activities. Even though the environment has limited resources, it demonstrates how computing resources can be provided through a cloud-based environment.

---

## Storage Resources

The main storage device observed in the Linux environment was **`/dev/vda1`**, with a total capacity of **19 GB**. At the time of checking, approximately **5.4 GB was used** and **13 GB was available**.

The environment also had mounted filesystems such as `/boot`, `/boot/efi`, `/run`, `/dev/shm`, and `/run/lock`.

### Purpose

Storage resources are used to save operating system files, applications, configurations, and other data. Unlike RAM, storage keeps information available even when it is not actively being used.

### Importance in Cloud Computing

Storage is important in cloud computing because applications and services need a reliable place to store their files and data. Cloud storage also allows organizations to keep large amounts of information without having to depend entirely on physical storage devices located on-site.

### Relation to the KillerCoda Environment

The `/dev/vda1` filesystem provides the main disk space used by the Ubuntu environment. It stores the operating system, laboratory files, applications, and other resources needed while working in KillerCoda.

---

## Networking Resources

The Linux environment has the hostname **`ubuntu`** and the IP addresses **`172.30.1.2`** and **`172.17.0.1`**.

### Purpose

Networking resources allow computers, applications, and other resources to communicate with each other. IP addresses provide network addresses that can be used to identify systems within their network environment.

### Importance in Cloud Computing

Networking is important in cloud computing because cloud resources need to communicate with users, applications, storage services, and other systems. A properly configured network allows cloud applications to be accessed and allows different resources to work together.

### Relation to the KillerCoda Environment

The hostname `ubuntu` identifies the Linux environment, while the IP addresses identify network addresses assigned to the environment. These networking details demonstrate how the KillerCoda server participates in a network and communicates with other resources.

---

## Operating System

The Linux environment is running **Ubuntu 24.04.4 LTS**, with the codename **Noble**. The kernel version is **6.8.0-136-generic**.

### Purpose

An operating system manages the computer's hardware and provides the environment where applications and commands can run. It acts as an interface between the user, applications, and the underlying hardware resources.

### Importance in Cloud Computing

The operating system is important in cloud computing because cloud servers need an operating environment to manage compute, storage, networking, and applications. Linux distributions such as Ubuntu are commonly used in cloud environments because they provide a flexible command-line environment for managing servers and applications.

### Relation to the KillerCoda Environment

Ubuntu is the operating system running inside the KillerCoda environment. It provides the terminal and system tools I used throughout this laboratory to inspect resources, manage files, create documentation, and work with Git and GitHub.

---

## Component Summary

| **Infrastructure Component** | **Observed Example** | **Main Purpose** |
|---|---|---|
| **Compute Resources** | Intel Xeon E312xx, 1 CPU core, 1.9 GiB RAM | Provides processing power and memory for running workloads |
| **Storage Resources** | `/dev/vda1`, 19 GB | Stores the operating system, applications, and data |
| **Networking Resources** | Hostname `ubuntu`, IP addresses `172.30.1.2` and `172.17.0.1` | Enables communication and identifies the system within its network |
| **Operating System** | Ubuntu 24.04.4 LTS, kernel `6.8.0-136-generic` | Manages system resources and provides the environment for applications and commands |

---

## Conclusion

Examining the KillerCoda environment helped me understand that cloud infrastructure is made up of several components that work together. Compute resources provide processing power, storage resources keep data, networking resources allow communication, and the operating system manages these resources and provides the environment where applications can run.

Although the KillerCoda environment is a simple Linux server, it demonstrates the same basic concepts found in larger cloud infrastructures. This activity helped me connect the system information I gathered from Linux commands with the infrastructure concepts discussed in cloud computing.
