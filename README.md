# 🗄️ db-backup-sync

**db-backup-sync** is a lightweight infrastructure tool that automates the transfer of database backup files from a database server to remote servers or centralized storage.

It helps ensure backups are safely replicated, reducing the risk of data loss and offloading storage from the primary DB server.

---

## 🚀 Features

- 📦 Copies database backup files to remote servers  
- 🔁 Supports scheduled automation (cron jobs)  
- 🌐 Works over SSH (secure transfer)  
- 🧹 Can be extended for backup rotation & cleanup  
- ⚡ Lightweight and easy to deploy  

---

## 🏗 Use Case

This tool is designed for environments where:

- A database server generates periodic backups  
- Backups must be stored on:
  - Backup servers  
  - Storage servers  
  - NAS / remote infrastructure  
- You want to automate and standardize the transfer process  

---

## 🛠 How It Works

1. Database server generates backup files (e.g., `.bak`, `.sql`, `.dump`)  
2. `db-backup-sync` detects or targets those files  
3. Files are transferred to remote destination(s) using `scp` or `rsync`  
4. (Optional) Logs the transfer status  

---

## 📂 Project Structure

db-backup-sync/
│
├── scripts/
│ └── db-backup-sync.sh
│
├── config/
│ └── backup.conf

---
## ⚙️ Configuration

Example `config/backup.conf`:

SOURCE_DIR="/var/backups/database"
REMOTE_USER="backupuser"
REMOTE_HOST="192.168.1.50"
REMOTE_DIR="/data/db-backups"
SSH_KEY="/home/user/.ssh/id_rsa"

---
## ▶️ Usage

### Manual Run

```bash
bash scripts/db-backup-sync.sh

🔐 Requirements

Linux server

SSH access to remote server

scp or rsync installed

SSH key authentication recommended

🧠 Future Improvements

Backup rotation & old file cleanup

Compression before transfer

Multi-destination replication

Email/Slack notifications

Integrity verification (checksum)

⚠️ Notes

Ensure sufficient storage on the remote server

Test SSH connectivity before automation

Monitor logs regularly

📜 License

MIT License







│
└── logs/
└── backup.log
