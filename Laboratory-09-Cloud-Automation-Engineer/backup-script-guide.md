# ⚙️ Backup Script Guide

---

## 01 | 💻 Backup Script

The `backup.sh` script automates the process of backing up application data. It creates a backup directory if one does not exist and compresses the application folder into a `.tar.gz` archive. A timestamp is included in the filename to help identify backups created at different times.

### Full Script Code

```bash
#!/bin/bash
# Automated Backup Script for CloudNova Technologies

SOURCE_DIR="app-data"
BACKUP_DIR="backups"
TIMESTAMP=$(date +"%Y%m%d_%H%M%S")

echo "Initiating automated backup..."

# Create the backup directory if it does not exist
mkdir -p $BACKUP_DIR

# Compress the source directory into a tarball (.tar.gz)
tar -czf $BACKUP_DIR/backup_$TIMESTAMP.tar.gz $SOURCE_DIR

echo "Backup completed successfully at $TIMESTAMP!"
```

### How the Script Works

| Command or Variable | Description |
|---|---|
| `#!/bin/bash` | Tells the system to use Bash to execute the script. |
| `SOURCE_DIR="app-data"` | Defines the folder containing the application data to back up. |
| `BACKUP_DIR="backups"` | Defines where the backup archives will be stored. |
| `TIMESTAMP=$(date +"%Y%m%d_%H%M%S")` | Generates a timestamp for the backup filename. |
| `echo` | Displays messages in the terminal to show the progress of the script. |
| `mkdir -p $BACKUP_DIR` | Creates the backup directory if it does not already exist. |
| `tar -czf` | Creates a compressed archive of the application directory. |

---

## 02 | 🔐 File Permissions

By default, a newly created Bash script may not have permission to run as an executable program. When I first tried running `./backup.sh`, the terminal returned a *Permission denied* error.

To fix this, I used the following command:

```bash
chmod +x backup.sh
```

The `chmod` command changes file permissions, while `+x` adds execute permission. After running this command, I was able to execute the script using `./backup.sh` and verify that the compressed backup file was created successfully.

**Key takeaway:** Setting the correct file permissions allows a script to run while keeping Linux file access under control.

---

## 03 | ⏰ Cron Job Configuration

To avoid running the backup script manually every day, I configured a cron job using the Linux crontab editor.

### Cron Expression

```cron
0 2 * * * /root/backup.sh
```

This configuration schedules the backup script to run every day at 2:00 AM, based on the system's clock and time zone.

### Breakdown of the Five Time Fields

| Field | Value | Meaning |
|---|---|---|
| Minute | `0` | Runs at minute zero. |
| Hour | `2` | Runs at 2:00 AM. |
| Day of Month | `*` | Runs on every day of the month. |
| Month | `*` | Runs every month. |
| Day of Week | `*` | Runs every day of the week. |

The asterisk (`*`) means every applicable value for that field.

### Command Used to Configure the Schedule

```bash
env EDITOR=nano crontab -e
```

After adding the cron expression and saving the file, I used the following command to check that the schedule was installed:

```bash
crontab -l
```

The output should display `0 2 * * * /root/backup.sh`, confirming that the cron entry is saved.

---

## 04 | 📌 Summary

Through this activity, I learned how to create a Bash script, give it execution permission, and configure a cron job for scheduled backups. These steps demonstrate how Linux automation can reduce repetitive manual work and help make routine backup tasks more consistent.

---

*CCM101 – Cloud Computing | Laboratory Activity 9*
