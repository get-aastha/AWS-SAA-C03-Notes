# Amazon DynamoDB

- provides replication across multiple AZs
- NoSQL database hence it is fast and felxible schema
- low cost and auto-scaling
- sub millisecond latency
- no maintenance required/ always available
- made of tables

- **Provisioned Mode** Specify the capacity beforehand and pay for it
- **On-Demand Mode** No capacity planning needed bcuz of auto scaling; pay for what you use (more expensive)

- Use cases 
    - Processing financial transactions
    - Fulfilling and managing orders
    - Building multiplayer games
    - Coordinating actions across distributed components or services
    - for rapidly evolving schema

## DynamoDB Accelerator(DAX)
- helps resolve read congestion by caching with less latency
- any read operatin from app to DynamoDB will first go to DAX cluster and check if data is already there; if it is there, it will be returned directly
- similar to ElastiCache (used for storing heavy changes)

## DynamoDB Streams
- less retention, limited no. of consumers compared to Kinesis Data Streams

## DynamoDB Global Tables
- more accessible with low latency in multiple regions
- active replication (when changes are made to one table, the other table gets updated)

# DynamoDB Backups

- On-demand backup and restore
    - Full backups at any time
    - Zero impact on table performance or availability
    - Operates within the same region as the source table

- Point-in-Time-Recovery (PITR)
    - Protects against accidental writes or deletes
    - Incremental backups
    - Not enabled by default
