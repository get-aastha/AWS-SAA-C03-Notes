# Volumes and Snapshots

## Volumes

- Volumes are virtual hard disks
- EC2 instances require at least 1 volume called the root device volume where the operating system is installed
- Volumes will be in the same availability zone as the EC2 instance they're attached to
- Volumes can be resized and volume types can be changed without stopping EC2 instances

## Snapshots

- Snapshot (copy) of volume (virtual disk)
- Snapshots are incremental
  - Only data that has changed since the last snaphot is moved to S3
- For a consistent snapshot, it is recommended to stop the EC2 instance to take a snapshot
- Snapshots don't include any cached data
- If you take a snapshot of an encrypted volume, the snapshot will automatically be encrypted
- Snapshots can only be shared in the region they were created in. To share across regions, they need to be copied into the destination region first