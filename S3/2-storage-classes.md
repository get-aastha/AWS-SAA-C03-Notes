# S3 Storage Classes

- **S3 Standard**
    - 99.99% availability
    - Highly available and Durable
    - Designed for frequently access data
    - Default S3 storage class
    - Use Case:
        - Websites
        - Content Distribution
        - Big Data Analytics
        - Mobile/Gaming apps


- **S3 Standard-Infrequent Access**
    - You pay to access the data
    - Use Case:
        - Long term storage
        - Backups
        - Disaster recovery
        - secondary backup copies

    - **S3 Standard-Infrequent Access (S3 Standard-IA)**
        - 99.9% availability, lower cost than S3-Standard
        - Designed for infrequently accessed data but requires rapid access


    - **S3 One Zone-Infrequent Access (S3 One Zone-IA)**
        - 99.5% availability, lower cost than S3-Standard-IA
        - Just like S3 Standard-IA, but data is stored in a single availability zone


- **Glacier**
    - 99.99% availability
    - Cheap storage
    - Pay each time you access the data
    - Use for long tern data archival
    - low latency
    - types- Instant retrieval, Flexible retrieval, Deep archive

- **S3 Intellignet Tiering**
    - 99.99% availability
    - Automatically moves your data to the most cost effective tier based on how frequently you access each object
    - monthly monitoring fees but no retrieval charges
    - Use Case
        - Unknown or unpredictable access patterns
