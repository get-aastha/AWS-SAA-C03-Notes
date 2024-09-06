# S3 (Simple Storage Service) Overview

- **Object Storage**
    - S3 is object based. You can upload any file type; Photos, Videos, Docments, Text Files, Code
    - You can store objects (files) in buckets (folders)
    -cheapest way for hosting static website
    
    **Univeral Namespace**
    - Buckets have a Univeral Namespace
    - All AWS accounts share the S3 namespace, so each bucket name needs to be globally unique
    - Buckets are created at regional level

    **Lifecycle Management**
    - Define rules to automatically transition objects to a cheaper storage tier or delete objects that are no longer required after a set period of time

- **Key:** The object name/full path (mountain.jpg)
- **Value:** The data
- **Metadata:** Data about the data you are storing (`last-modified`, `content-type`)


# Versioning

 Allows you to have multiple versions of an object within S3
**Version ID:** Allows you to store multiple versions of the same object.

## Advantages of Versioning
- All versions of an object are stored in S3.  This includes all writes and even if the object is deleted.
- Can be used to backup objects
- Once enabled, versioning cannot be disabled... only suspended. Prev versions won't be deleted.
- Versioning supports MFA


# Securing Data in S3
- **Server-Side Encryption**
    - You can default encryption on a bucket to encrypt all new objects when they are stored in a bucket

- **Bucket Policies**
    - Specify what actions are allowed or denied 
    - Allow user to **PUT** but not **DELETE** objects in a bucket

- **Access Control Lists (ACLs)**
    - Define which AWS accounts or groups are granted access and the type of access.
    - ACLs can be attached to individual objects (Object ACL) or to a bucket (Bucket ACL)

## Securing your bucket

- Buckets are private by default. You have to allow access to both the bucket and objects in the bucket for access
- You can make individual objects public by using **Access Control Lists (ACL)**.
- You can make entire buckets public using **bucket policies**.