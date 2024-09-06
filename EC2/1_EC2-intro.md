# EC2 Overview

# Elastic Compute Cloud (EC2)

- Secure, resizable compute capacity in the cloud
- Like a VM, only hosted in AWS
- You only pay for what you use

- renting virtual machines - EC2
- network attached
  - storing data using file based system - EFS
  - storing data on virtual drives - EBS
- distributing load across machines - ELB
- scaling services using auto scaling grps - ASG
- hardware - EC2 Instance

# Security Groups

- Security groups are virtual firewalls for a EC2 instance. By default, everything is blocked.
- To let all traffic access your EC2 instance, use 0.0.0.0/0
- Changes to security groups take effect immediately
- You can have any number of EC2 instances in a security group
- Multiple security groups can be attached to one EC2 instance
- All inbound traffic is blocked by default
- All outbound traffic is allowed by default
- They are specific to region


**SSH into EC2 Instance**
SSh allows you to connect to a remote machine using CLI/Putty

**EC2 Insatnce connect**
- Connect to your EC2 Instance within your browser using temp key
- No need to use Putty