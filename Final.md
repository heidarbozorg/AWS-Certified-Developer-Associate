# AWS Certified Developer – Associate Notes

## Cheat Sheet Table

| #  | Topic                                               | Summary                                                                 |
|----|-----------------------------------------------------|-------------------------------------------------------------------------|
| 1  | IAM Access Analyzer                                 | Detects public or cross-account access using resource-based policies.   |
| 2  | Access Control List (ACL) vs Trust Policy           | ACLs manage resource access; trust policies define who can assume a role.|
| 3  | IAM credential types for CodeCommit                 | Supports SSH keys, Git credentials, and AWS access keys.                |
| 4  | Lambda Authorizer vs Cognito User Pools            | Lambda for custom auth logic; Cognito for managed user auth.           |
| 5  | CloudFront Key Pairs - Root User                    | Only root can create CloudFront key pairs for signed URLs.             |
| 6  | X-Ray Sampling Feature                              | Controls which requests are traced to manage cost and detail.          |
| 7  | KMS encryption process                              | KMS stores CMKs and encrypts client data internally.                   |
| 8  | KMS direct encryption behavior                      | Up to 4 KB data can be encrypted directly; uses envelope encryption for larger data. |
| 9  | Backlog per Instance Metric in ECS with SQS         | Scales ECS tasks based on SQS messages divided by running tasks.       |
| 10 | Auto Scaling Group across Regions                   | ASGs are regional; cross-region scaling requires multiple ASGs.        |
| 11 | Elastic Beanstalk Instance Recovery                 | Replaces failed instances with last successful app version.            |
| 12 | How Elastic Beanstalk operates EC2 instances        | Uses ASG and ALB for launching, health checking, and versioning.       |
| 13 | Amazon EFS in ECS Fargate across AZs                | EFS must have mount targets in all AZs for multi-AZ Fargate tasks.     |
| 14 | AWS Budget Forecasting Delay                        | Requires ~5 weeks of usage data to generate forecast.                  |
| 15 | Immediate forecast if usage exists                  | Forecast available immediately if 5+ weeks of prior data exists.       |
| 16 | AWS CDK App Template                                | Generates project structure for defining infrastructure as code.       |
| 17 | CDK does not generate application code              | CDK defines infrastructure; you write app code like Lambda separately. |
| 18 | AWS Serverless Application Repository (SAR)         | Repository of reusable serverless apps built with AWS SAM.             |
| 1  | `appspec.yml` vs `buildspec.yml`           | `appspec.yml` is for CodeDeploy deployments; `buildspec.yml` is for CodeBuild builds. |
| 2  | `sam deploy`                               | Performs a full CloudFormation stack deployment from a SAM app.        |
| 3  | `sam sync`                                 | Rapidly updates code/config for existing resources, but cannot create new ones. |
| 4  | `cdk diff`                                 | Compares local CDK app with deployed stack to preview changes.         |
| 5  | `cdk deploy`                               | Synthesizes and deploys a CDK app to AWS via CloudFormation.           |
| 6  | EC2 Reserved Instances (Regional)          | Regional RIs offer cost savings without capacity reservation.          |
| 7  | EC2 Reserved Instances (Zonal)             | Zonal RIs include capacity reservation and are AZ-specific.            |
| 8  | EC2 Auto Scaling – ASGAverageCPUUtilization| Average CPU usage across ASG; commonly used in target tracking.        |
| 9  | EC2 Auto Scaling – ASGAverageNetworkOut    | Scales based on outbound network traffic from instances.               |
| 10 | EC2 Auto Scaling – ALBRequestCountPerTarget| Scales based on number of incoming ALB requests per instance.          |
| 11 | EBS AZ Locking                             | EBS volumes are locked to a single Availability Zone.                  |
| 12 | EBS Multi-Attach                           | `io1/io2` volumes support multi-attach to EC2 in the same AZ.          |
| 13 | EBS Cross-Region Restore                   | Snapshot → copy snapshot to another region → create new volume.        |
| 14 | Shared Volume (EFS)                        | EFS allows concurrent mounts from multiple EC2s across AZs.            |
| 15 | VPC Flow Logs                              | Captures IP-level metadata for VPC/Subnet/ENI traffic.                 |
| 16 | Subnet Logs                                | No standalone logs; use VPC Flow Logs at the subnet level.             |
| 17 | BGP Logs                                   | Logs for dynamic VPN routing behavior; visible via DescribeVpnConnections. |
| 18 | VPN Logs                                   | Monitor tunnel status and client connection logs via CloudWatch.       |
| 19 | DynamoDB On-Demand Backups                 | Manual full-table backups, stored in AWS-managed S3 (no direct access).|
| 20 | DynamoDB Point-in-Time Recovery (PITR)     | Automatically backs up data with second-level recovery up to 35 days.  |
| 21 | Export DynamoDB with Glue                  | ETL from DynamoDB to S3 using AWS Glue jobs; downloadable data.        |
| 22 | Export DynamoDB with EMR (Hive)            | Use Hive on EMR to query/export DynamoDB data to S3.                   |
| 23 | Export DynamoDB with Data Pipeline         | Scheduled DynamoDB table export to S3 (even cross-account).            |
| 24 | CloudFormation Parameter Types             | Includes basic types (String, Number) and AWS-specific resource types. |
| 25 | CFN Parameter Type – `AWS::EC2::KeyPair::KeyName` | Ensures user selects a valid EC2 KeyPair for SSH access.          |
| 26 | SNS Topic                                  | Core component to publish messages to multiple subscribers.            |
| 27 | SNS Subscription                           | Defines endpoint and protocol for receiving messages from topic.       |
| 28 | SNS Filter Policy                          | Controls message delivery to subscribers using message attributes.     |
| 29 | AWS CLI `--dry-run`                        | Tests IAM permissions for an action without actually executing it.     |
| 1  | CloudFormation Import/Export Syntax        | Use `Export`/`Fn::ImportValue` to share values across stacks           |
| 2  | Stack vs Subnet Concepts in CloudFormation | Understand stack structure and how subnets fit into CFN definitions    |
| 3  | Cognito Sync                               | Deprecated feature for cross-device data sync                          |
| 4  | SSM SecureString for Secrets               | Store secrets using encrypted parameters in SSM                        |
| 5  | ASG Detailed Monitoring                    | Enables 1-min metrics for faster auto scaling                          |
| 6  | ALB Target Types (Instance, IP, Lambda)    | ALB can route to EC2, IPs, or Lambda with different behaviors          |
| 7  | Standard CloudWatch EC2 Metrics            | Includes CPU, network, disk metrics; excludes memory                   |
| 8  | DynamoDB GSIs and LSIs                     | GSIs allow alternate PK/SK; LSIs allow alternate SK only               |
| 9  | CodeDeploy Lifecycle Hooks (In-Place)      | Six ordered hooks like ApplicationStop, BeforeInstall, etc.            |
| 10 | CloudTrail and S3 Object Ownership         | Logging only works if bucket owner also owns the object                |
| 11 | Invalidate API Gateway Cache               | Send `Cache-Control: max-age=0` to bypass API Gateway cache            |
| 12 | ElastiCache: Redis vs Memcached            | Use Redis for durability & structure; Memcached for speed & simplicity |
| 13 | EventBridge (CloudWatch Events) Rules      | Trigger Lambda, Step Functions, etc. based on events or schedule       |
| 14 | Ephemeral Ports in EC2/ELB Communication   | EC2 responds on ports 1024–65535; important for firewalls & NACLs      |
| 15 | CloudFormation CLI Commands                | Use `package`, `deploy`, `create-stack`, etc.                          |
| 16 | Lambda Package Size Limits                 | Max 50MB zipped (CLI), 250MB unzipped (via S3), 5x50MB for layers      |
| 17 | SSE-C and S3 + HTTP Restriction            | SSE-C requires HTTPS; HTTP requests are rejected                       |
| 18 | STS Service Responsibilities               | Temporary creds, role assumption, error decoding                       |
| 19 | Redis Cluster and Cluster Mode             | Cluster mode enables sharding, HA; cluster-aware client required       |
| 20 | Send Data to Kinesis from EC2              | Use SDK, CLI, Kinesis Agent, or KPL depending on source                |
| 21 | CloudWatch Logs Encryption via KMS         | Associate CMK with log group and grant access                          |
| 22 | ALB Host-Based vs Path-Based Routing       | Route based on domain (host-header) or URL path (path-pattern)         |
| 1  | S3 Versioning & Null Version     | Objects uploaded before versioning have a `null` version ID. Uploads after enabling versioning get unique IDs. After a delete, a **delete marker** is created with its own version ID. |
| 2  | S3 Select                        | Allows querying a **subset of data** from S3 objects using **SQL-like expressions**. Reduces data transfer and processing costs. Supports CSV, JSON, and Parquet. |
| 3 | S3 CLI: Pagination Options       | Use `--max-items` (limit total returned), `--page-size` (items per API call), `--starting-token` (resume pagination). All useful for **efficient batch processing**. |
| 4  | Amazon Macie                     | A security service that uses ML to scan S3 for **PII** and sensitive data. Outputs **findings**, not enforcement. Good for **compliance** and **data classification**. |
| 5  | SQS FIFO Options                     | Use `MessageGroupId` (required), `MessageDeduplicationId`, or `ContentBasedDeduplication` to ensure **strict ordering** and **exactly-once processing** in FIFO queues. |
| 6  | SQS: MessageGroupId in Standard Queue| `MessageGroupId` is **only supported in FIFO queues**. Standard queues do not guarantee order or support this field. Attempting to use it causes a validation error. |
| 7  | Beanstalk Docker & Custom Platforms        | Choose from Single-container Docker, Multi-container (via ECS), or Custom Platforms (via Packer). `Dockerrun.aws.json v1` for single; `v2` for multi-container. |
| 8  | Beanstalk Worker & `cron.yaml`             | In a Worker environment, use `cron.yaml` to define scheduled jobs. Beanstalk will POST to defined routes based on cron expressions (in UTC). |
| 9  | Beanstalk: Rolling with Additional Batch   | Deployment strategy that **adds a temporary batch of instances** during updates, ensuring **no downtime**. Great for production apps needing high availability. |
| 10 | AWS KMS: Data Key Caching  | Use the **AWS Encryption SDK** with **data key caching** to reduce KMS API costs. Caches data keys in memory for reuse with TTL and usage limits. |
| 11 | IAM Authorization with SigV4 & API GW | Use **SigV4-signed requests** for **IAM-based auth** in API Gateway (`AWS_IAM`). Great for service-to-service. Not suitable for public apps. |
| 12 | Public APIs with API Keys             | Use **API Keys** in API Gateway to **identify and throttle** access from known clients (web, mobile). Combine with Lambda authorizer for better validation. |
| 13 | EC2 Instance Metadata     | Query instance metadata at `http://169.254.169.254/latest/meta-data/` to get instance ID, IP, security groups, etc. Use **IMDSv2** (token-based) for improved security. |
| 14 | X-Ray Annotations & Indexes  | Use **Annotations** (simple key-value pairs) for **filtering** and **grouping traces** in X-Ray; searchable types: `string`, `number`, `boolean`. Metadata is **not indexed** and used for debugging only. |
| 15 | AWS CodeStar     | AWS CodeStar provides an all-in-one UI to create, manage, and deploy applications using CodeCommit, CodeBuild, CodePipeline, and CodeDeploy. Great for small teams and rapid setup. |
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
| 1  | Built-in Encryption in S3              | Uses SSE-S3, SSE-KMS, or SSE-C to encrypt objects at rest         |
| 2  | SSE-S3 Costs and Limitations           | Free, low-latency, but not reusable for other services            |
| 3  | S3 Event Notifications to SNS          | Trigger SNS topic when an object is uploaded to S3                |
| 4  | S3 Replication (SRR/CRR)               | Auto-copy of objects within or across AWS regions                 |
| 5  | Origin Group in CloudFront             | Ensures failover between two origins in CloudFront                |
| 6  | MOCK Integrations in API Gateway       | Returns predefined responses with no backend                      |
| 7  | RCU and WCU in DynamoDB                | Defines throughput for read/write operations                      |
| 8  | DAX in DynamoDB                        | In-memory cache for fast, low-latency reads                       |
| 9  | Batch Operations in DynamoDB           | Reduce API calls by grouping reads/writes                         |
| 10 | DynamoDB Pricing                       | Charges for storage, RCU/WCU, and optional features               |
| 11 | Gateway VPC Endpoint for DynamoDB      | Secure, internet-free access from VPC to DynamoDB                 |
| 12 | SQS Extended Client                    | Stores large payloads in S3, only references in SQS               |
| 13 | SQS Dead-Letter Queues (DLQ)           | Captures messages that fail processing after max retry attempts   |
| 14 | Dedicated Worker in Beanstalk          | Processes SQS messages using EC2-based app                        |
| 15 | Beanstalk vs Lambda for SQS            | Choose based on latency, cost, and flexibility                    |
| 16 | Triggering Beanstalk Workers           | Works only with SQS, not direct events or HTTP                    |
| 17 | Elastic Beanstalk Serverless?          | Not serverless—manages EC2 with auto scaling                      |
| 18 | ecs.config File                        | Controls ECS agent behavior on EC2 instances                      |
| 19 | Step Functions Workflow Types          | Standard = durable, Express = high-speed                          |
| 20 | AWS Glue                               | Discover, catalog, and transform data using visual or code jobs   |
| 21 | CloudFormation Pseudo Parameters       | Built-in variables like AWS::AccountId or AWS::Region             |
| 22 | AWS CloudFormation Change Sets         | Previews changes to resources before applying an update           |

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

## Topic Descriptions

### 1. Built-in Encryption in S3  
Provides server-side encryption options (SSE-S3, SSE-KMS, SSE-C) to secure data at rest in S3 buckets.

### 2. SSE-S3 Costs and Limitations  
SSE-S3 is free and transparent but limited to internal S3 use; you can't use the keys externally (e.g., in Lambda or EC2).

### 3. S3 Event Notifications to SNS  
Automatically notifies an SNS topic when an object is uploaded to a bucket, enabling event-driven workflows.

### 4. S3 Replication (SRR/CRR)  
Automatically replicates objects within the same region (SRR) or across regions (CRR) for backup, compliance, or performance.

### 5. Origin Group in CloudFront  
Allows failover between a primary and secondary origin in CloudFront to ensure content delivery continuity.

### 6. MOCK Integrations in API Gateway  
Lets API Gateway return predefined responses without invoking a backend—great for prototyping or testing.

### 7. RCU and WCU in DynamoDB  
Defines how much data you can read/write per second. Essential for performance tuning and avoiding throttling.

### 8. DAX in DynamoDB  
An in-memory cache that dramatically reduces read latency in read-heavy DynamoDB applications.

### 9. Batch Operations in DynamoDB  
`BatchGetItem` and `BatchWriteItem` allow efficient grouping of multiple operations, reducing costs and API calls.

### 10. DynamoDB Pricing  
Covers charges for provisioned/on-demand throughput, data storage, secondary indexes, and other features.

### 11. Gateway VPC Endpoint for DynamoDB  
Enables private access to DynamoDB from your VPC without exposing traffic to the public internet.

### 12. SQS Extended Client  
Enables sending messages > 256 KB by storing the payload in S3 and passing a reference in SQS.

### 13. SQS Dead-Letter Queues (DLQ)  
Stores failed SQS messages after retry attempts are exhausted—critical for debugging and guaranteed processing patterns.

### 14. Dedicated Worker in Beanstalk  
Runs a background EC2-based worker that polls SQS and processes jobs (e.g., email, image processing).

### 15. Beanstalk vs Lambda for SQS  
Choose Lambda for short, fast tasks; use Beanstalk when you need long processing or more control over the environment.

### 16. Triggering Beanstalk Workers  
Elastic Beanstalk Worker Environments are **only** triggered by polling SQS—not by direct HTTP or SNS triggers.

### 17. Elastic Beanstalk Serverless?  
No—Beanstalk automates EC2 management but is not serverless; you still pay for infrastructure.

### 18. ecs.config File  
Customizes ECS agent behavior on EC2 instances (e.g., setting cluster name, enabling metadata, IAM roles for tasks).

### 19. Step Functions Workflow Types  
Standard Workflows support durable, long-running processes; Express Workflows are designed for high-speed, short-lived flows.

### 20. AWS Glue  
A serverless ETL service for crawling, transforming, and loading structured and semi-structured data across AWS data stores.

### 21. CloudFormation Pseudo Parameters  
Automatically available variables like `AWS::Region` and `AWS::AccountId` that make templates dynamic and reusable.

### 22. AWS CloudFormation Change Sets  
Safely preview the differences between the current stack and proposed changes—prevents unexpected infrastructure drift.

---

## License

MIT License ⇒ free to use, modify, and share. Contributions welcome!
