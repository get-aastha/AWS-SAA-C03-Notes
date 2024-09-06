# EFS Overview

## Elastic File System (EFS) can be accessed in multi-AZ

- Works with EC2 instances that are in multiple availablity zones
- Centralized/shared storage for multiple EC2 instances
- Highly available and scalable
- Expensive
- Uses NFSv4 protocol
- Compatible with Linux based AMI (Windows support currently not available)
- Encryption at rest using Key Management System (KMS)
- Auto-scaling file system - no capacity planning

**Storage Tiers**

EFS provides storage tiers and lifecycle management allowing you to  move data from one tier to another based on parameters you setup