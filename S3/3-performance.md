# Optimizing S3 Performance

## S3 Performance
- The more folder and subfolders you have in your S3 bucket, the better the performance
- You can get better performance by spreading your reads across different prefixes (Folders inside a bucket)
- **S3 Inventory** Get object list and use S3 Select to filter out objects


## S3 Uploads
### Multipart Uploads
- Recommended for files **over 100MB**
- Required for files **over 5GB**
- Parallelize uploads (increase efficiency)

## S3 Downloads
### S3 Byte-Range Fetches
- Parallelize downloads by specifying byte ranges
- If there's a failure in the download, it's only for a specific byte range
- Can be used to download partial amounts of a file

### S3 Transfer Accelaration
- increase transfer speed by transferring file to AWS edge location which will forward the date to S3 bucket in the target region
- compatible with multi-port upload


## S3 Replication

- After you enable replication, only new objects are replicated
- You can replicate existing objects using batch operation (manually)
- Can replicate delete markers from source to target
- no **chaining of replication**
    - if bucket 1 has replication into bucket 2 which has replication into bucket 3, then objects created in bucket 1 are not replicated to bucket 3
    - same rule applies to creating bucket rule
- **Cross Region Replication (CRR)** low latency, replication across acounts
- **Same Region Replication (SRR)** replication bw production and test accounts

