# Relational Database Service (RDS) Overview
- Data in a relational database is organized into rows and columns, which form a table.
- Managed databse enabling auto-scaling

- RDS Database Types
  - MySQL
  - PostgreSQL
  - Amazon Aurora

- RDS Workloads
  - Online transaction processing (OLTP) workloads (Designed to process large numbers of small transactions)

## Read Replicas
- A read replica is a read-only copy of your primary database
- When your application does a query, it would query the read replica and not your database, reducing load on your database
- Read replicas can cross different availablity zones
- Automatic backups must be enabled to deploy a read replica

- Multi-AZ is an exact copy of your database used for disaster recovery while read replicas are for scaling and improving performance

**You can only encrypt DB when it created. To encrypt it midway, use snapshot**

# Amazon Aurora

- Amazon Aurora is MySQL and PostgreSQL compatible
- offer high performance with low latency read replicas across multiple regions
- Two copies of your data are contained in each availabity zone, with a minimum of 3 availability zones (6 copies of your data)
- Aurora is designed to handle the loss of up to 2 copies of data without affecting database write availability and up to 3 copies without affecting read availability
- Aurora storage is self-healing.  Data blocks and disks are continously scanned for errors and repaired automatically

- Backups
    - Automated backups are always enabled with Aurora DB instances
    - Backups and snapshots do not impact performance
    - Aurora snapshots can be shared with other AWS accounts

- Aurora Serverless
    - Auto-scalling configuration for the MySQL and PostgreSQL compatible versions of Aurora
    - Aurora serverless DB clusters startup, shutdown, scale up/down based on application needs
    - Only pay for what you use (on-demand)
    - Use Cases
        - Infrequent or unpredictable workloads


# NoSQL databases:
- DynamoDB: for key-calue pairs
- ElastiCache: for key/value pair, session management, heavy code changes, more reads less writes, caching
- Neptune: for graph structures (inter connected data)
- DocumentDB: for MongoDB structures
- Kespaces: for Apache Cassandra structures, multi region replication, useful for IOT
- OpenSearch (JSON): for unstructured searches

# Object Storage:
- S3: for large objects
- Glacier: for backups/archives (cheaper)

# Data Warehouse
- Redshift: for OLAP (Online analytical Processing), parallel query processing, columnar storage
- Athena: to run SQL queries directly on S3, enables users to query from multiple sources, pay per query, ad-hoc analysis
- EMR: for big data processing
- QLDB (Quantum Ledger Database): automatic indexing hence fast seraching history & auditing
