#  Final Reflection

## 📖 Introduction

Completing Missions 1 through 10 in CCM101 gave me a better understanding of cloud computing and how it works in real-world applications. Throughout the course, I was introduced to different concepts and activities involving cloud services, computer resources, networking, Linux, system security, and automation.

At first, I thought cloud computing was mainly about storing files online or accessing applications through the internet. However, as I worked through the different missions, I realized that there is much more to it. It also involves setting up and managing servers, configuring networks, deploying applications, protecting data, and making sure that everything runs properly.

These activities helped me connect the concepts discussed in class with actual technical tasks and gave me a better idea of what goes on behind the systems and services we use every day.

## ☁️ Learning Experience from Missions 1–9

The first nine missions introduced me to the basic concepts and practical applications of cloud computing. Each activity helped me understand a different part of how cloud environments are planned, configured, and managed.

I learned about cloud infrastructure and its major components, such as computing resources, storage, and networking. I also became familiar with cloud service providers like Amazon Web Services (AWS), Microsoft Azure, and Google Cloud Platform (GCP). Through these lessons, I understood why choosing the right resources is important when planning and building a cloud-based system.

The hands-on activities also gave me the opportunity to work with Linux commands. I learned how to check system information, monitor CPU and memory usage, and view available disk space. These exercises helped me become more comfortable using the Linux environment and understanding how a server manages its resources.

Working with PowerShell was another useful experience. I learned how scripts can simplify repetitive tasks and make system administration more efficient. Rather than performing every task manually, scripts can help gather information and automate certain processes.

Aside from the technical activities, I also learned the importance of security and proper resource management. A system should not only work as expected but should also be configured properly to protect its data and prevent unnecessary access.

## 🏗️ Experience in Mission 10 – Enterprise Cloud Architect

Mission 10 was one of the most meaningful activities for me because it allowed me to apply the concepts and skills I had learned from the previous missions in a single project.

For this mission, I developed **CloudNova**, a web application infrastructure hosted on Ubuntu Server using Oracle VirtualBox.

I started by configuring the virtual machine and its network connections so that my Windows laptop could communicate with the Ubuntu Server and access the WordPress website. I then installed Docker and Docker Compose to deploy WordPress and MariaDB as separate but connected containers.

One thing I learned from this setup was the importance of persistent storage. Using Docker volumes allows important application files and database information to remain available even when containers are stopped or recreated. This helped me understand why proper data storage is important when managing applications.

I also worked on securing the server by configuring UFW, limiting SSH access, disabling password authentication, and using SSH key authentication. I applied firewall rules to control access to the website and kept the database from being directly exposed to the host network.

Another important part of the project was database backup automation. I created a Bash script that generates a database backup, compresses the file, checks its validity, and removes backups that are more than seven days old. I also configured Cron to run the script automatically every day.

Working on CloudNova helped me see how virtualization, networking, containers, storage, security, and automation are connected. Instead of studying these topics separately, I was able to experience how they work together in an actual server environment.

## ⚠️ Challenges and Lessons Learned

Throughout the project, I encountered several challenges, particularly when configuring the network, troubleshooting SSH connections, and setting up firewall rules.

There were times when my Windows laptop could not connect to the Ubuntu Server, and some configurations affected how the application could be accessed. I had to review the settings, check the network connections, and perform several tests before identifying and resolving the problems.

The backup automation was also a learning experience. I needed to understand how to connect to the database, generate backup files, compress them, and schedule the process using Cron. There were also times when commands did not work as expected, which required me to review their syntax and understand what went wrong.

Although these problems sometimes made the process challenging, they taught me to be more patient and careful when working with technical configurations. I realized that troubleshooting is an important part of system administration, and not everything will work perfectly on the first attempt.

Most importantly, I learned that it is better to understand what a command or configuration does before applying it, especially when dealing with security settings, network access, and important data.

## 🎯 Conclusion

Overall, CCM101 has helped me develop a better understanding of cloud computing, not just through theories but also through actual hands-on activities.

From Missions 1 to 10, I gained experience with cloud services, Linux, PowerShell, virtualization, Docker, networking, security, and automation. Each mission contributed to my learning and helped me become more familiar with the tools and technologies used in managing cloud environments.

Developing CloudNova was a valuable experience because it allowed me to put what I learned into practice. It also showed me that building and maintaining a working system involves more than simply installing software. It requires proper planning, configuration, security, testing, and continuous maintenance.

I know that I still have a lot to learn, but completing these activities has given me a stronger foundation and more confidence in handling technical tasks. I hope to apply the knowledge and experience I gained from this course to future projects and continue improving my skills as I work toward becoming an IT professional.
