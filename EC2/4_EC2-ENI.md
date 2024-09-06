**Elastic IPs**
- when you stop and then start an EC2 Instance, it can change its public IP
- Elastic IP is used for having a fixed public IP for your instance


# Networking with EC2

**ENI: Elastic Network Interface**

- Attached by default to an EC2 instance
- Primary private IPV4
- One elastic IP per private IPV4
- One public IPV4
- One or more security groups
- Many IPv6 Addresses
- MAC Addresses
- Bound to specific availability zone
- You can create and move independent ENIs on EC2 instances for failover

- **ENI Use Cases:**
  - Create a management network
  - Use network or security appliances in your VPC
  - Create dual-homed instances with workloads/roles on distinct subnets
  - Allows for private network addresses
  - Create a low budget, highly available solution



# Hibernation in EC2
- RAM state is preserved so instance boot is faster
- RAM state is written to EBS volume
- Instance cannot be hibernated more than 60 days