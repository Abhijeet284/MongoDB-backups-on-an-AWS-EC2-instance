# ☁️ MongoDB Backup Automation on AWS

## 📌 Overview

In this project, I built an automated system to back up a MongoDB database hosted on an AWS EC2 instance. The solution uses scripting and cron jobs to eliminate manual intervention and ensures secure storage of backups in AWS S3.

---

## 🚀 Features

* Automated MongoDB backups using cron jobs
* Backup creation using `mongodump`
* Timestamp-based backup storage
* Secure upload to AWS S3
* Improved reliability and reduced manual effort

---

## 🛠️ Tech Stack

* AWS EC2
* AWS S3
* MongoDB
* Bash Scripting
* Linux (Cron Jobs)

---

## 🧠 Problem Statement

Manual database backups are inefficient and prone to errors. This project provides an automated and reliable backup solution using cloud infrastructure.

---

## ⚙️ Architecture

The system consists of three layers:

1. **Database Layer**
   MongoDB running on an AWS EC2 instance
   
   <img width="1008" height="697" alt="Screenshot 2025-04-10 225048" src="https://github.com/user-attachments/assets/d1e8a4f9-f21d-4582-a2bf-ad9131c96781" />


3. **Automation Layer**
   Bash script using `mongodump` and cron jobs

4. **Storage Layer**
   AWS S3 bucket for storing backups securely

---

## 🧩 How It Works

1. MongoDB runs on an EC2 instance
2. A backup script creates database dumps using `mongodump`
3. Cron job schedules automatic execution daily
4. Backup files are uploaded to AWS S3
5. Logs help track backup status

---

## 🔧 Implementation

### Backup Command

```bash
mongodump --out /home/ubuntu/backups/$(date +%F-%T)
```

### Cron Job (Runs Daily at 2 AM)

```bash
0 2 * * * /home/ubuntu/backup.sh
```

### Upload to S3

```bash
aws s3 cp /home/ubuntu/backups s3://mongodb-backup-storage --recursive
```

---

## 📊 Results

* Successfully automated MongoDB backups
* Eliminated manual intervention
* Ensured secure cloud storage using AWS S3

---

## ⚠️ Challenges Faced

* Setting up cron jobs correctly
* Managing AWS permissions for S3 access
* Verifying backup and restore process

---

## 🔮 Future Improvements

* Add encryption for backups
* Implement monitoring using AWS CloudWatch
* Optimize storage using incremental backups

---

## 👨‍💻 Author

**Abhijeet Pandit**
