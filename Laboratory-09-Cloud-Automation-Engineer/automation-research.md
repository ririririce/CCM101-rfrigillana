# ⚙️ Automation Research: The Language of Automation

---

## 01 | 💻 Bash Script

A Bash script is a file that contains a series of Linux commands written together to perform a specific task. Instead of entering each command manually in the terminal, we can put them in one script and execute them whenever needed. The `#!/bin/bash` line, also known as the *shebang*, is placed at the beginning of the file to tell the system which interpreter should be used to execute the script. In cloud operations, Bash scripts are useful for automating repetitive tasks, managing files, and performing system maintenance more efficiently.

**Key Point:** Bash scripts help reduce manual work by combining multiple commands into one executable file.

```bash
#!/bin/bash
echo "Starting automated backup..."
```

---

## 02 | 📁 Variables

Variables allow programmers to store values, such as directory paths, file names, or other information that a script needs to use. For example, `BACKUP_DIR="backups"` stores the name of the folder where backup files will be saved, while `$BACKUP_DIR` allows us to access that value in other parts of the script. Using variables instead of repeatedly typing the same folder path makes the script more organized and easier to maintain. If the backup location changes in the future, we can simply update the variable rather than modifying every command that uses the path.

**Key Point:** Variables make scripts easier to update, reuse, and maintain.

```bash
BACKUP_DIR="backups"
echo "$BACKUP_DIR"
```

---

## 03 | ⏰ Cron Job

A cron job is a Linux scheduling feature that allows commands or scripts to run automatically at specific times or on a recurring schedule. It is configured through a *crontab* file, where we specify the schedule using time fields for the minute, hour, day of the month, month, and day of the week. Cron jobs are essential in cloud operations because many administrative tasks, such as creating backups, cleaning temporary files, and running maintenance scripts, need to be performed regularly. By scheduling these tasks, system administrators can reduce manual work, avoid forgetting important operations, and maintain more consistent server management.

**Key Point:** Cron jobs ensure that scheduled tasks run automatically without requiring someone to execute them manually every time.

```cron
0 2 * * * /root/backup.sh
```

*Schedule explanation: This command runs the backup script every day at 2:00 AM.*

---

### 📌 Summary

| Concept | Main Purpose |
|---|---|
| 💻 Bash Script | Automates a sequence of Linux commands |
| 📁 Variables | Store values for reuse within a script |
| ⏰ Cron Job | Runs commands automatically on a schedule |

---

*Laboratory Activity 9 — The Cloud Automation Engineer*  
*CCM101 | Cloud Computing*
