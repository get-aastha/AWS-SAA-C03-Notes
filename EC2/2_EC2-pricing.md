# EC2 Pricing Options

- **On-Demand**

  - Pay by the hour or second based on the instance you are running
  - Flexible - No long term commitment
  - Use Case:
    - Applications with short term, unpredictable workloads that can't be interrupted
    - Applications being developed or tested on Amazon EC2 for the first time

- **Reserved**

  - Reserve capacity for 1-3 years
  - Reserved instances operate at a regional level, so you can transfer a RI to a different region
  - Can be used with Lambda and Fargate
  - Types of reserved instances
    - Standard
      - Up to 72% off on-demand price
      - fixed region/RI for the reserved period
    - Convertible
      - Up to 54% off on-demand price
      - Has the option to change to a different reserved instance
  - Use Case:
    - Applications with predictable usage and steady state
    - Applications that require a reserved capacity

- **Spot**

  - Purchase unused capacity
  - Discount of up to 90%
  - If other use for capacity is found, it can be taken away from you so not recommended for applications that need to be continously running
  - Use Case:
    - Applications that have flexible start and end times
    - Urgent need for large amounts of computing capacity
      - Image Rendering
      - Genomic Sequencing
      - Alogrithmic Trading engines

      **Spot Instances**
      
      - Spot instances allow you to take advantage of unused EC2 capacity
      - Spot instances should be used for stateless, fault tolerant, or flexible applicaitons or anywhere you don't need persistent storage
      - Examples
        - Big Data
        - Containarized workloads
        - HPC
        - Test/Dev workloads

      - Spot blocks can be used to block Spot instances from being terminated
      - Spot fleet is a collection of Spot instances and (optionally) On-Demand instances


- **Dedicated Hosts**
  - A physical EC2 server dedicated to your use. The most expensive option
  - Can be purchased on-demand or hourly
  - Use Case:
      - Applications or licensing that does not support multi-tenant virtualization
      - Windows Server
    - Microsoft SQL Server
    - Linux Enterprise Server

  
    **Dedicated Instances vs Dedicated Hosts**
    - Dedicated Instances run on hardware dedicated to you while Dedicated hosts are servers dedicated to you
    - Dedicated Instances may share hardware with some other instances in the saem account while Dedicated hosts does not allow multiple instances to run in the same server
