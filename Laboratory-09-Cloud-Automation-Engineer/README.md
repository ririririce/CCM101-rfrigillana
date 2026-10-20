# ⚙️ Laboratory 09: Cloud Automation Engineer

> **CCM101 – Cloud Computing**  
> *Mission 09 | CloudNova Technologies*

---

## 🎯 Mission Overview

  Congratulations! Your ability to secure cloud environments has proven you are ready for the highest 
level of operations. You have been promoted to the Cloud Automation and DevOps Team at CloudNova 
Technologies. 
  Up until now, you have been acting as a traditional systems administrator—typing commands manually 
one by one. In large enterprise environments scaling to thousands of servers, manual administration is too slow 
and highly prone to human error. To survive at scale, you must learn to automate. 
  Using the KillerCoda Playground, you will step into the role of a Cloud Automation Engineer. You will 
learn the basics of Bash shell scripting, create an automated backup routine, assign executable permissions, and 
configure the Linux Cron scheduler to run your code autonomously. 
Remember: **If you have to do a task more than twice in the cloud, you should automate it.**

---

## 📌 Objectives

- Understand the fundamental syntax of a Bash shell script, including variables and basic commands.
- Use a command-line text editor (nano) to write and save executable scripts.
- Modify Linux file permissions using the chmod command.
- Understand task scheduling and the syntax of a Linux crontab.
- Document automation code and Cron job configurations using Markdown.
- Complete the final chapter of your GitHub Cloud Computing Portfolio.

---

## 💻 Commands Executed

The following commands were used throughout the laboratory activity.

| Command | Purpose |
|---|---|
| `mkdir app-data` | Creates the sample application data directory. |
| `echo "This is critical client data." > app-data/data.txt` | Creates a test file containing sample data. |
| `nano backup.sh` | Opens Nano to create or edit the Bash script. |
| `./backup.sh` | Executes the backup script after permissions are configured. |
| `chmod +x backup.sh` | Adds execute permission to the script. |
| `ls -l backups/` | Lists the generated backup archives. |
| `crontab -l` | Displays the current user's scheduled cron jobs. |
| `env EDITOR=nano crontab -e` | Opens the crontab editor using Nano. |

### Automated Backup Schedule

```cron
0 2 * * * /root/backup.sh
```

This cron entry schedules the backup script to run every day at 2:00 AM, according to the system's clock and time zone.

---

## 🛠️ Skills Learned

- **Bash Scripting:** I learned how to combine Linux commands into a script to automate the backup process.
- **File Permissions:** I learned how `chmod +x` allows a script to be executed as a program.
- **File Compression:** I practiced using `tar` to create compressed archives of application data.
- **Task Scheduling:** I learned how to configure and verify cron jobs for automatically running scripts.
- **Technical Documentation:** I practiced explaining commands, script behavior, and scheduling configurations using Markdown.

This activity helped me see how automation can make repetitive tasks easier to manage. I also learned that scripts and scheduled jobs must be configured carefully to ensure that they run as expected.
---

*CCM101 Cloud Computing Portfolio | Laboratory Activity 9*
