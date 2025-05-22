# AWS Certified Developer – Associate: Mock Exam 6 Notes

## Cheat Sheet Table

| #  | Topic                                                | Summary                                                                 |
|----|------------------------------------------------------|-------------------------------------------------------------------------|
| 1  | [S3: Eventual Consistency on Bucket Deletion](#1-s3-eventual-consistency-on-bucket-deletion) | Deleted bucket might still appear due to eventual consistency.         |
| 2  | [S3: Simultaneous Writes & Event Notifications](#2-s3-simultaneous-writes--event-notifications) | Simultaneous writes to non-versioned object may trigger only one event.|
| 3  | [S3: Encryption by Default](#3-s3-encryption-by-default) | Region-wide setting; can't disable encryption for individual resources.|
| 4  | [S3: CloudFront Signed URLs/Cookies](#4-s3-cloudfront-signed-urls--cookies) | Used to restrict access to S3 via CloudFront; not related to Cognito.  |
| 5  | [CloudFront: Cognito Integration Limitation](#5-cloudfront-cognito-integration-limitation) | CloudFront does not natively support Cognito authentication.           |
| 6  | [CloudFront: Origin Group Failover](#6-cloudfront-origin-group-failover) | Only one primary and one secondary origin per group; not load-balanced.|
| 7  | [EBS: CreateVolume Not in CloudTrail (EC2 launch)](#7-ebs-createvolume-not-in-cloudtrail-ec2-launch) | EBS volumes created during EC2 launch won’t log `CreateVolume` in CT.  |
| 8  | [EBS: Region-Wide Encryption by Default](#8-ebs-region-wide-encryption-by-default) | Cannot turn off encryption per volume once default is enabled.         |
| 9  | [EC2: Multi-AZ RDS](#9-ec2-multi-az-rds) | Provides automatic failover and high availability via standby instance.|
| 10 | [RDS vs Read Replicas](#10-rds-vs-read-replicas) | Multi-AZ is for HA, Read Replicas are for scalability (read traffic).  |
| 11 | [STS: Role Assumption by API Gateway](#11-sts-role-assumption-by-api-gateway) | API Gateway uses STS to assume an IAM role for CloudWatch logging.     |
| 12 | [STS: Why It’s Needed](#12-sts-why-its-needed) | Used to get temporary credentials to write logs securely.              |
| 13 | [IAM Policy: `"Resource": "*"` Meaning](#13-iam-policy-resource--meaning) | Grants permissions for all resources; used when targets are dynamic.   |
| 14 | [SQS: Max Number of Messages](#14-sqs-max-number-of-messages) | You can retrieve up to 10 messages in a single `ReceiveMessage` call.  |
| 15 | [CodeDeploy: Deployment Group](#15-codedeploy-deployment-group) | Defines where and how deployments occur; can target EC2, Lambda, or ECS.|
| 16 | [CodeDeploy: Deployment Configurations](#16-codedeploy-deployment-configurations) | Controls deployment speed (AllAtOnce, HalfAtATime, OneAtATime).        |
| 17 | [CodeDeploy: Rollback and Hooks](#17-codedeploy-rollback-and-hooks) | Supports lifecycle events, alarm-based rollbacks, and load balancer integration.|
| 18 | [ECR: `get-login --no-include-email`](#18-ecr-get-login---no-include-email) | Authenticates Docker to ECR; now deprecated in favor of `get-login-password`.|
| 19 | [DynamoDB: Global Tables for Global Users](#19-dynamodb-global-tables-for-global-users) | Use Global Tables to reduce latency for globally distributed users.     |
| 20 | [DynamoDB: Conflict Handling in Global Tables](#20-dynamodb-conflict-handling-in-global-tables) | Last writer wins (based on timestamp); replication is asynchronous.     |

---

## 📘 Detailed Notes

### 1. S3: Eventual Consistency on Bucket Deletion
S3 uses eventual consistency for bucket listings. When you delete a bucket and immediately call `ListBuckets`, the deleted bucket might still appear briefly due to propagation delays across regions.

### 2. S3: Simultaneous Writes & Event Notifications
In non-versioned S3 buckets, if two clients write to the same key simultaneously, only one event notification might be sent. This is due to write coalescing and eventual consistency.

### 3. S3: Encryption by Default
When you enable encryption by default in a region, all new volumes and snapshots are encrypted automatically, and you can't disable encryption for individual resources unless you disable the setting region-wide.

### 4. S3: CloudFront Signed URLs / Cookies
To restrict access to S3 content via CloudFront, use signed URLs or cookies. These provide time-limited access and are not tied to Cognito authentication.

### 5. CloudFront: Cognito Integration Limitation
CloudFront does not natively support Cognito User Pools for authentication. To enforce auth, you can use Lambda@Edge to validate JWTs or use API Gateway/ALB in front of CloudFront.

### 6. CloudFront: Origin Group Failover
In an origin group, CloudFront uses a **primary origin** and fails over to a **secondary origin** based on error status codes or timeouts. Only one origin is active at a time.

### 7. EBS: CreateVolume Not in CloudTrail (EC2 launch)
When EBS volumes are created as part of an EC2 launch, the `CreateVolume` API call is not explicitly logged in CloudTrail, as it is initiated internally by EC2.

### 8. EBS: Region-Wide Encryption by Default
Once you enable default encryption for EBS in a region, every new volume is encrypted, and you cannot create unencrypted volumes unless you disable the setting.

### 9. EC2: Multi-AZ RDS
Multi-AZ RDS deployments offer high availability by maintaining a standby instance in a different AZ and enabling automatic failover during outages or maintenance.

### 10. RDS vs Read Replicas
Multi-AZ is for high availability (failover), while Read Replicas are for scaling read traffic. Replication in Read Replicas is asynchronous.

### 11. STS: Role Assumption by API Gateway
API Gateway uses AWS STS to assume an IAM role and get temporary credentials that allow it to write logs to CloudWatch.

### 12. STS: Why It’s Needed
STS allows temporary, secure access to AWS services. API Gateway uses it to assume roles securely for logging or other delegated tasks.

### 13. IAM Policy: `"Resource": "*"` Meaning
The wildcard `*` means “all resources.” This is often used when the exact resource ARN is unknown, such as in dynamically created log groups or streams.

### 14. SQS: Max Number of Messages
The `ReceiveMessage` API call in SQS allows retrieving up to **10 messages** at once. This is the maximum, and the actual number returned may be fewer.

### 15. CodeDeploy: Deployment Group
Defines where (EC2, Lambda, ECS) and how the deployment happens. It uses tags, ASGs, or function names to target resources.

### 16. CodeDeploy: Deployment Configurations
Controls rollout strategy — options like `AllAtOnce`, `HalfAtATime`, or `OneAtATime` define how many targets are updated concurrently.

### 17. CodeDeploy: Rollback and Hooks
Deployment groups can define rollback conditions (e.g., CloudWatch alarms) and use `appspec.yml` to execute lifecycle event hooks like `BeforeInstall`, `AfterInstall`.

### 18. ECR: `get-login --no-include-email`
This older command logs in Docker to ECR. It's deprecated in favor of `get-login-password | docker login --password-stdin`.

### 19. DynamoDB: Global Tables for Global Users
Global Tables let you deploy tables in multiple regions, allowing read/write access near your users and reducing latency.

### 20. DynamoDB: Conflict Handling in Global Tables
Global Tables use **last-writer-wins** conflict resolution based on timestamps. Replication is **asynchronous**, so simultaneous writes can be overwritten.

---

