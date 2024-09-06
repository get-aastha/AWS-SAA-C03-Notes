# S3 Encryption

## Types or Encryption

- **Encryption in Transit**
    - SSL/TLS
    - HTTPS

- **Encryption at Rest: Server-Site Encryption**
    - **SSE-S3:**  S3 managed keys; 256-bit encryption (most common)
    - **SSE-KMS:**  Key Management Service
    - **SSE-C:** Customer Provided Keys

- **Encryption at Rest: Client-Side Encryption**
    - Encrypt files before uploading them into S3

## Enforcing Server-Side Encryption
- **Console**
    - Select the encryption setting on your S3 Bucket
    - Easiest method - checkbox in console
- **Bucket Policies**
    - Enforce encryption using a bucket policy
    - Deny all **PUT** requests that don't include the `x-amz-server-side-encryption` parameter in the request header
    
    
# S3 Object Lock

## What is S3 Object Lock
- You can use S3 Object lock to store objects using a write once, read many (WORM) model
- It can help prevent objects from being deleted/modified for a fixed amount of time, or indefinitely
- S3 Object lock can be used to meet regulatory requirements that require WORM storage, or add an extra layer of protection against object changes or deletion

## S3 Object Lock Modes
- **Governance Mode**
    - Users can't overwrite/delete an object version or alter it's lock settings unless they have special permissions

- **Compliance Mode**
    - Protected objects can't be overwritten/deleted by any user, including the root user
    - The objects retention mode can't be changed and it's retention period can't be shortened

## Retention Periods
- Protects an object version for a fixed amount of time
- After the retention period has expired, the object version can be overwritten/deleted unless you also place a legal hold on the object version.

## Legal Hold
- S3 Object lock that prevents an object from being overwritten/deleted.
- Remains in effect until removed
- Legal holds do not have an associated retention period and can be freely assigned and removed by any user with the following permission:  `s3:PutObjectLegalHold`

# Glacier Vault Lock
- Allows you to deploy and enforce compliance controls for individual S3 Glacier Vaults with a vault lock policy
- Allows you to specify controls such as WORM in a lock policy and lock the policy from future edits
- Once locked, the policy can't be changed