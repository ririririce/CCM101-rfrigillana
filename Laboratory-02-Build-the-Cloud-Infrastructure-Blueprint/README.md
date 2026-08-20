# Laboratory Activity 2 – Build the Cloud Infrastructure Blueprint

## Mission Overview

Congratulations,  
Your onboarding has been successfully completed, and your Cloud Computing Portfolio has been approved by 
your supervisor. 
CloudNova Technologies has now assigned you to your first official project. 
Before deploying cloud services, every cloud engineer must understand the infrastructure that powers modern 
cloud computing. Your mission is to investigate the components of cloud infrastructure, identify how compute, 
storage, networking, and identity services work together, and document your findings as if you were preparing 
technical documentation for a client. 
Using the KillerCoda Playground, Linux tools, official cloud documentation, and your GitHub Cloud Computing 
Portfolio, you will complete a series of engineering tasks that simulate the planning phase of a cloud deployment. 
Remember: Great cloud engineers build systems—but exceptional cloud engineers document and justify 
every design decision. 

---

## Objectives

The objectives of this laboratory activity were to:

- Explain the major components of cloud infrastructure.  
- Investigate the hardware and software resources available in a Linux environment.  
- Differentiate compute, storage, networking, and identity resources.  
- Interpret the relationship between cloud infrastructure components.  
- Create professional technical documentation using Markdown.  
- Continue building a structured GitHub Cloud Computing Portfolio.  

---

## Cloud Infrastructure Components

During the activity, I identified four main infrastructure components in the KillerCoda Linux environment.

### Compute Resources

The environment provided an **Intel Xeon E312xx processor**, with **1 CPU core** and approximately **1.9 GiB of RAM**. These resources provide the processing power and memory needed to run commands, applications, and other processes inside the Linux environment.

### Storage Resources

The main storage device was `/dev/vda1`, which had a total capacity of **19 GB**. At the time of checking, around **5.4 GB was being used** and approximately **13 GB was still available**.

Other mounted filesystems were also present, including `/boot`, `/boot/efi`, `/run`, `/dev/shm`, and `/run/lock`.

### Networking Resources

The Linux environment had the hostname **`ubuntu`** and the IP addresses **`172.30.1.2`** and **`172.17.0.1`**. These allow the system to be identified within its network environment and support communication between networked resources.

### Operating System

The server was running **Ubuntu 24.04.4 LTS** with kernel version **6.8.0-136-generic**. The operating system provides the environment where commands and applications can run while also managing the available system resources.

### Digimart Cloud Infrastructure

For the cloud infrastructure design, I used **Digimart**, a fictional e-commerce company.

The diagram contains the required components:

| **Component** | **Digimart Example** | **Purpose** |
|---|---|---|
| **User** | Digimart Customer | Uses the e-commerce application |
| **Internet Connection** | Internet | Allows the customer to access Digimart |
| **Network** | Digimart Virtual Network | Connects the cloud resources |
| **Compute Resource** | Digimart E-Commerce Application Server | Runs the e-commerce application |
| **Storage Resource** | Digimart Cloud Storage | Stores product, order, and application data |

The basic flow of the design is:

**Digimart Customer → Internet → Digimart Network → Compute Resource → Storage Resource**

The completed diagram is saved as:

`cloud-architecture.png`

inside the `screenshots` folder.

---

## Tools Used

The following tools were used during the activity:

- **KillerCoda** — Used to access and work with the cloud-based Linux environment.
- **Ubuntu Linux** — Used as the operating system for the cloud server investigation.
- **Git** — Used to track changes and manage the laboratory files.
- **GitHub** — Used to store the repository and maintain the laboratory portfolio.
- **Nano** — Used to create and edit Markdown files directly from the terminal.
- **Tree** — Used to view the organization of folders and files.
- **Web Browser** — Used to access the official documentation of AWS, Microsoft Azure, and Google Cloud.
- **ChatGPT** — Used to help with grammar, organization, explanations, and ideas while preparing the documentation.

---

## Linux Commands Executed

The following commands were used throughout the laboratory activity to inspect the Linux environment, manage files and directories, and manage the GitHub repository.

| **Command** | **Description** |
|---|---|
| `git clone` | Creates a local copy of a GitHub repository in the Linux environment. |
| `lsb_release -a` | Displays detailed information about the installed Linux distribution, including its name, version, release, and codename. |
| `uname -r` | Displays the version of the Linux kernel currently running on the system. |
| `lscpu \| grep "Model Name"` | Displays the CPU model information by filtering the `lscpu` output for the processor model name. |
| `nproc` | Displays the number of processing units or CPU cores available to the system. |
| `free -h` | Displays the total, used, free, and available memory in a human-readable format. |
| `df -h /` | Displays the disk capacity and usage of the root filesystem. |
| `df -h` | Displays disk space usage for all mounted filesystems in a human-readable format. |
| `hostname` | Displays the hostname of the Linux system. |
| `hostname -I` | Displays the IP addresses assigned to the Linux system. |
| `cd` | Changes the current working directory or navigates to a specified directory. |
| `mkdir` | Creates a new directory or folder. |
| `touch` | Creates a new empty file. |
| `nano` | Opens a terminal-based text editor for creating and editing files, including Markdown files. |
| `tree` | Displays files and directories in a tree-like structure. |
| `cd ..` | Moves one level up to the parent directory. |
| `cd ..` | Moves another level up in the directory structure. |
| `git add .` | Stages all new and modified files in the repository for the next commit. |
| `git commit -m "show folder"` | Saves the staged changes to the local Git history with a descriptive commit message. |
| `git push` | Uploads committed changes from the local repository to GitHub. |

---

## Skills Learned

This activity helped me improve several technical skills that are useful in cloud computing and system administration.

I learned how to inspect a Linux environment using commands such as `lscpu`, `free`, `df`, `hostname`, and `hostname -I`. I also became more comfortable navigating folders, creating files, editing Markdown files with Nano, and viewing the structure of a project using `tree`.

I also gained a better understanding of how compute, storage, networking, and operating systems work together as part of cloud infrastructure. Comparing AWS, Microsoft Azure, and Google Cloud helped me recognize that different cloud providers may use different names for services that perform similar functions.

Another important skill I practiced was using Git and GitHub. I learned how to clone a repository, stage changes, create commits, and push my work to GitHub.

---

## Challenges Encountered

One challenge I encountered was understanding the information displayed by some Linux commands. The output contained technical terms and system information that I needed to understand before I could properly record them in my documentation.

I also encountered difficulties while working with Git and GitHub, particularly when pushing changes to the repository. I experienced a **403 permission error**, which made me check the repository and authentication settings before continuing.

Another challenge was organizing the Markdown files so that the documentation would be clear and easy to read. I had to become more familiar with Markdown formatting and learned how to use headings, tables, code formatting, and links to make the files more organized.

Despite these challenges, working through them helped me become more comfortable with the Linux terminal, GitHub, and technical documentation.

---

## Conclusion

This laboratory activity gave me a better understanding of how the basic parts of cloud infrastructure work together. By examining the KillerCoda Linux environment, I was able to see actual examples of compute, storage, networking, and operating system resources rather than only learning about them theoretically.

The comparison of AWS, Microsoft Azure, and Google Cloud also helped me understand that cloud providers may use different service names while providing similar fundamental capabilities. Designing the Digimart infrastructure gave me an opportunity to apply these concepts to a simple real-world scenario.

Overall, this activity helped me improve my Linux, Git, GitHub, cloud computing, and technical documentation skills. It also gave me a better foundation for understanding how cloud infrastructure can be designed and managed.
