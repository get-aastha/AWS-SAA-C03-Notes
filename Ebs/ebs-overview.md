# IOPS vs Throughput

**IOPS**

- Measures number of read/write operations per second
- Important metric when tracking latency for high transaction workloads
- If high throughput is a requirement, choose Provisioned IOPS SSD (io1 or io2)

**Throughput**

- Measures number of bits read/written per second
- Important metric for large datasets and complex queries
- If dealing with large datasets is a requirement, choose Throughput Optimized HDD (st1)

# EBS Overview

# Elastic Block Store (EBS) on-premise, cannot be accessed in multi-AZ

- Storage volumes that can be attached to an EC2 instance (virtual hard disk)
  - Install Operating System
  - Create File System
  - Install Applications
  - Store Files

- Designed for mission critical, production workloads
- Highly Available: Automatically replicated within a single availablity zone to protect against hardware failures
- Scalable: Dymanically change volume size or type with no downtime or performance impact to your systems
  - You may have to resize file system

## Volume Types

**General Purpose SSD (GP2)**

- Balance of price and performance
- Volumes smaller than 1 TB can burst up to 3,000 IOPS
- Good for boot volumes or development/test applications that are not latency sensitive

**General Purpose SSD (GP3)**

- Ideal for applications that require high performance and low cost
  - MySQL
  - Virtual Desktops
  - Hadoop Analytics
- Users can scale up to 16,000 IOPS

**Provisioned IOPS SSD (io1)**

- High performance, most expensive
- Up to 64,000 IOPS per volume
- **Use if you need more than 16,000 IOPS**
- **Designed for I/O intensive applications (Databases, latency sensitive workloads)**

**Provisioned IOPS SSD (io2)**

- Same price as io1
- Latest generation
- Higher durability and more IOPS
  - 500 IOPS per GB up to 64,000 IOPS
- **Designed for I/O intensive applications (Databases, latency sensitive workloads)**

**Throughput Optimized HDD (st1)**

- Low cost HDD volume
- Maximum throughput of 500 MB/s per volume
- Designed for frequently accessed, throughput intensive workloads
  - Big data, data warehouses, ETL, log processing
  - Good for storing large amounts of data
- Cannot be a boot volume

**Cold HDD (SC1)**

- Lowest cost option
- Maximum throughput of 250 MB/s per volume
- Designed for applications where performance is not a factor
  - File server
- Cannot be a boot volume


# EBS Encryption

- EBS Encryption encrypts a volume with a data key using AES-256 algorithm.
- EBS Encryption uses AWS Key Management Service (AWS KMS) customer master keys (CMK) when creating encrypted volumes and snapshots
- Data at rest is encrypted within the volume
- All data moving between the EC2 instance and the volume is encrypted
- All snapshots are encrypted
- Encryption and decryption are handled transparently - the user does not need to do anything
- Encryption has minimal impact on latency
- Copying an unencrypted snapshot allows encryption
- Snapshots of encrypted volumes are encrypted
- Root device volumes can be encrypted on creation