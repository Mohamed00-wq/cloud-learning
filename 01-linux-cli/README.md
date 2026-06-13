# 🐧 Linux CLI Fundamentals

## 💻 Navigation Commands
Navigation commands allow users to move through the Linux file system and inspect directory contents. The cd command moves between folders using relative paths (e.g., cd Documents) or absolute paths (e.g., cd /home/user). Key shortcuts include ~ (home directory), .. (parent directory), and - (previous directory). The pwd command displays the current location, while ls lists files and directories, with options like -l for details and -a for hidden files. The tree command recursively lists files and directories in a tree-like format. The locate command quickly finds files by name using a prebuilt database.

## 🗂️ Linux Filesystem Structure
The Linux filesystem follows the Filesystem Hierarchy Standard (FHS). Key directories include:

| Directory | Purpose |
|-----------|---------|
| /home | User home directories |
| /etc | System-wide configuration files |
| /var | Variable data (logs, caches, databases) |
| /dev | Device files representing hardware |

## 🗂️ File Management Commands

| Command | Description |
|---------|-------------|
| mkdir | Creates new directories |
| mkdir -p | Creates directory and all parent directories |
| rmdir | Removes empty directories only |
| rm | Deletes files |
| rm -r | Recursively removes directories |
| touch | Creates empty files or updates timestamps |
| cp | Copies files (use -r for directories) |
| mv | Moves or renames files/directories |

⚠️ rmdir is safe — refuses non-empty directories. rm -r is destructive — double-check before using.

## ⚙️ Process Management Commands

| Command | Description |
|---------|-------------|
| ps | Snapshot of current processes (ps aux for all) |
| top / htop | Real-time monitoring |
| kill <PID> | Terminates a process |
| kill -9 <PID> | Force-stops a process |
| bg / fg | Manage background/foreground processes |
| command & | Runs a command in the background |

## ☁️ Cloud-Ready Linux Skills

| Topic | Why it matters |
|-------|---------------|
| SSH & remote access | Managing cloud VMs |
| Text processing (grep, sed, awk) | Parsing logs and configs |
| File permissions (chmod, chown) | Security basics |
| Networking (curl, wget, ping) | Debugging connectivity |
| systemctl & journalctl | Managing services |
| Shell scripting | Automation |
| Environment variables | Configuring apps and SDKs |
| Archiving (tar, gzip) | Logs and backups |
| Users & groups | Multi-tenant systems |
| Disk usage (df, du, lsblk) | Monitoring storage |
