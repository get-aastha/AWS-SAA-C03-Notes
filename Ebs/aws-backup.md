# AWS Backup

AWS Backup allows you to consolidate backups across multiple AWS services, including:
- EC2
- EBS
- EFS
- FSx for Lustre
- FSx for Windows File Server
- AWS Storage Gateway
- Can also include RDS and DynamoDB

AWS Backup can be used with organizations

**Benefits**

- Central Management
  - Centralize backups across multiple AWS services and accounts

- Automation
  - Create automated backup schedules and retention policies
  - Create lifecycle policies - Expire unnecessary backups after a period of time

- Encryption
  - Backups can be encrypted in transit or at rest


# EC2 Hibernation

- EC2 hibernation preserves the in-memory RAM on persistent storage (EBS)
- Much faster to boot.. operating system is not reloaded
- Instance RAM must be less than 150 GB
- Includes the following instance families: C3, C4, C5, M3, M4, M5, R3, R4, and R5
- Instances can't be hibernated for more than 60 days
- Available for On-Demand and Reserved instances


# FSx Overview

**FSx for Windows**

- Fully managed Windows file system
- Provides (easier) migration for Windows based applications that need file storage to AWS

**FSx for Lustre**

- Fully mananged file system optimzed for intensive workloads
- High perfomance computing
- Machine learning
- for linux