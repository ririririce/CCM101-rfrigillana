# Automation Research: The Language of Automation

## 1. Bash Script

A Bash script is a file that contains Linux commands that can run one after another, so we don't have to type each command manually. The `#!/bin/bash` line at the beginning tells Linux to use Bash to run the commands written in the file.

## 2. Variables

Variables help us store information, such as folder paths, so we can easily use them again in our script. For example, using `$BACKUP_DIR` saves us from typing the same folder path repeatedly and makes the script easier to update if we need to change the location.

## 3. Cron Job

A cron job allows Linux to run commands or scripts automatically at a specific time or on a regular schedule. It is useful in cloud operations because it helps handle repetitive tasks, such as backing up important files, without needing someone to run them manually every time.
