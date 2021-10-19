# AWS Concepts

### Introduction of EBS (Elastic Block Store)
- https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-volumes.html


### Benefits of EBS volumes
- https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-volumes.html#EBSFeatures


### EBS Product Demonstration (LAB)


### Introduction to EFS (Elastic File System)
- https://aws.amazon.com/about-aws/whats-new/2015/04/introducing-amazon-efs/

### Comparison between EBS and EFS
- EBS: Can only be accessed by a single Amazon EC2 instance. EFS: Can be accessed by 1 to 1000s of EC2 instances from multiple AZs, concurrently
- EFS: File storage service for use with AWS EC2. EFS can be used as network file system for on-premise servers too using AWS Direct Connect.

### EFS Product Demonstration (LAB)


### Introduction to S3 (Simple Storage Service) Bucket and Object
- https://docs.aws.amazon.com/AmazonS3/latest/userguide/Welcome.html

### Object Versioning Storage classes
- https://docs.aws.amazon.com/AmazonS3/latest/userguide/storage-class-intro.html
- https://d1.awsstatic.com/product-marketing/S3/Amazon_S3_StorageClasses_Infographic_2020.pdf

### Types of Storage classes Life cycle management


### Static Website Hosting
- https://docs.aws.amazon.com/AmazonS3/latest/userguide/EnableWebsiteHosting.html


### When should I use Amazon EFS vs. Amazon S3 vs. Amazon Elastic Block Store (EBS)?
- Amazon EFS is a file storage service for use with Amazon compute (EC2, containers, serverless) and on-premises servers. Amazon EFS provides a file system interface, file system access semantics (such as strong consistency and file locking), and concurrently-accessible storage for up to thousands of Amazon EC2 instances.
- Amazon EBS is a block level storage service for use with Amazon EC2. Amazon EBS can deliver performance for workloads that require the lowest-latency access to data from a single EC2 instance.
- Amazon S3 is an object storage service. Amazon S3 makes data available through an Internet API that can be accessed anywhere.
