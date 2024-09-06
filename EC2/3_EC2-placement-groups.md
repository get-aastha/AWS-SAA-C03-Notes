# EC2 Placement Groups

## Three types of placement groups

**Cluster Placement Group** for low latency

- Great network
- Grouping of instances within a single availablity zone
- Recommended for applications that need low network latency, high network throughput
- When one rack fails, all its components fail

**Spread Placement Group** for high availability

- Group of instances placed on distinct underlying hardware/span multiple availablity zones
- Recommended for applications that have a small number of critical instances that should be kept seperate from each other
- When requirement is high availability- when one instance grp fails, others remain unaffected
- Distaster Managemnet Recovery

**Partition Placement Group**

- Used for multiple instance with dedicated network and power sources
- May or may not be in same availability zones
- Each partion placement group has it's own set of server rack
- Each rack has it's own network and power source
- No two partions share the same rack, allow you to isolate the impact of a hardware failure within an application
- Used in Hadoop, Cassandra, Kafca

**Other notes**

- Only certain instance types can be launched into a placement group
  - Compute optimized
  - GPU
  - Memory optimized
  - Storage optimized

- Placement groups can't be merged
- AWS recommends homogenous instances within a cluster placement group
- Existing instances can be moved into a placement group if they are in a stopped state
- Instance in placement groups can be removed via the AWS CLI or SDK (not console)