# AWS Certified Developer – Associate Notes

## Cheat Sheet Table (Logically Grouped)

| # | Topic | Summary |
|----|-------|---------|
| 1 | ALB Host-Based vs Path-Based Routing | Route based on domain (host-header) or URL path (path-pattern) |
| 2 | ALB Target Types (Instance, IP, Lambda) | ALB can route to EC2, IPs, or Lambda with different behaviors |
| 3 | ASG Detailed Monitoring | Enables 1-min metrics for faster auto scaling |
| 4 | AWS Budget Forecasting Delay | Requires ~5 weeks of usage data to generate forecast. |
| 5 | AWS CDK App Template | Generates project structure for defining infrastructure as code. |
| 6 | AWS CLI `--dry-run` | Tests IAM permissions for an action without actually executing it. |
| 7 | AWS CloudFormation Change Sets | Previews changes to resources before applying an update |
| 8 | AWS CodeStar | AWS CodeStar provides an all-in-one UI to create, manage, and deploy applications using CodeCommit, CodeBuild, CodePipeline, and CodeDeploy. Great for small teams and rapid setup. |
| 9 | AWS Glue | Discover, catalog, and transform data using visual or code jobs |
| 10 | AWS KMS: Data Key Caching | Use the **AWS Encryption SDK** with **data key caching** to reduce KMS API costs. Caches data keys in memory for reuse with TTL and usage limits. |
| 11 | AWS Serverless Application Repository (SAR) | Repository of reusable serverless apps built with AWS SAM. |
| 12 | Access Control List (ACL) vs Trust Policy | ACLs manage resource access; trust policies define who can assume a role. |
| 13 | Amazon EFS in ECS Fargate across AZs | EFS must have mount targets in all AZs for multi-AZ Fargate tasks. |
| 14 | Amazon Macie | A security service that uses ML to scan S3 for **PII** and sensitive data. Outputs **findings**, not enforcement. Good for **compliance** and **data classification**. |
| 15 | Auto Scaling Group across Regions | ASGs are regional; cross-region scaling requires multiple ASGs. |
| 16 | BGP Logs | Logs for dynamic VPN routing behavior; visible via DescribeVpnConnections. |
| 17 | Backlog per Instance Metric in ECS with SQS | Scales ECS tasks based on SQS messages divided by running tasks. |
| 18 | Batch Operations in DynamoDB | Reduce API calls by grouping reads/writes |
| 19 | Beanstalk Docker & Custom Platforms | Choose from Single-container Docker, Multi-container (via ECS), or Custom Platforms (via Packer). `Dockerrun.aws.json v1` for single; `v2` for multi-container. |
| 20 | Beanstalk Worker & `cron.yaml` | In a Worker environment, use `cron.yaml` to define scheduled jobs. Beanstalk will POST to defined routes based on cron expressions (in UTC). |
| 21 | Beanstalk vs Lambda for SQS | Choose based on latency, cost, and flexibility |
| 22 | Beanstalk: Rolling with Additional Batch | Deployment strategy that **adds a temporary batch of instances** during updates, ensuring **no downtime**. Great for production apps needing high availability. |
| 23 | Built-in Encryption in S3 | Uses SSE-S3, SSE-KMS, or SSE-C to encrypt objects at rest |
| 24 | CDK does not generate application code | CDK defines infrastructure; you write app code like Lambda separately. |
| 25 | CFN Parameter Type – `AWS::EC2::KeyPair::KeyName` | Ensures user selects a valid EC2 KeyPair for SSH access. |
| 26 | CloudFormation CLI Commands | Use `package`, `deploy`, `create-stack`, etc. |
| 27 | CloudFormation Import/Export Syntax | Use `Export`/`Fn::ImportValue` to share values across stacks |
| 28 | CloudFormation Parameter Types | Includes basic types (String, Number) and AWS-specific resource types. |
| 29 | CloudFormation Pseudo Parameters | Built-in variables like AWS::AccountId or AWS::Region |
| 30 | CloudFront Key Pairs - Root User | Only root can create CloudFront key pairs for signed URLs. |
| 31 | CloudTrail and S3 Object Ownership | Logging only works if bucket owner also owns the object |
| 32 | CloudWatch Logs Encryption via KMS | Associate CMK with log group and grant access |
| 33 | CodeDeploy Lifecycle Hooks (In-Place) | Six ordered hooks like ApplicationStop, BeforeInstall, etc. |
| 34 | Cognito Sync | Deprecated feature for cross-device data sync |
| 35 | DAX in DynamoDB | In-memory cache for fast, low-latency reads |
| 36 | Dedicated Worker in Beanstalk | Processes SQS messages using EC2-based app |
| 37 | DynamoDB GSIs and LSIs | GSIs allow alternate PK/SK; LSIs allow alternate SK only |
| 38 | DynamoDB On-Demand Backups | Manual full-table backups, stored in AWS-managed S3 (no direct access). |
| 39 | DynamoDB Point-in-Time Recovery (PITR) | Automatically backs up data with second-level recovery up to 35 days. |
| 40 | DynamoDB Pricing | Charges for storage, RCU/WCU, and optional features |
| 41 | EBS AZ Locking | EBS volumes are locked to a single Availability Zone. |
| 42 | EBS Cross-Region Restore | Snapshot → copy snapshot to another region → create new volume. |
| 43 | EBS Multi-Attach | `io1/io2` volumes support multi-attach to EC2 in the same AZ. |
| 44 | EC2 Auto Scaling – ALBRequestCountPerTarget | Scales based on number of incoming ALB requests per instance. |
| 45 | EC2 Auto Scaling – ASGAverageCPUUtilization | Average CPU usage across ASG; commonly used in target tracking. |
| 46 | EC2 Auto Scaling – ASGAverageNetworkOut | Scales based on outbound network traffic from instances. |
| 47 | EC2 Instance Metadata | Query instance metadata at `http://169.254.169.254/latest/meta-data/` to get instance ID, IP, security groups, etc. Use **IMDSv2** (token-based) for improved security. |
| 48 | EC2 Reserved Instances (Regional) | Regional RIs offer cost savings without capacity reservation. |
| 49 | EC2 Reserved Instances (Zonal) | Zonal RIs include capacity reservation and are AZ-specific. |
| 50 | ElastiCache: Redis vs Memcached | Use Redis for durability & structure; Memcached for speed & simplicity |
| 51 | Elastic Beanstalk Instance Recovery | Replaces failed instances with last successful app version. |
| 52 | Elastic Beanstalk Serverless? | Not serverless—manages EC2 with auto scaling |
| 53 | Ephemeral Ports in EC2/ELB Communication | EC2 responds on ports 1024–65535; important for firewalls & NACLs |
| 54 | EventBridge (CloudWatch Events) Rules | Trigger Lambda, Step Functions, etc. based on events or schedule |
| 55 | Export DynamoDB with Data Pipeline | Scheduled DynamoDB table export to S3 (even cross-account). |
| 56 | Export DynamoDB with EMR (Hive) | Use Hive on EMR to query/export DynamoDB data to S3. |
| 57 | Export DynamoDB with Glue | ETL from DynamoDB to S3 using AWS Glue jobs; downloadable data. |
| 58 | Gateway VPC Endpoint for DynamoDB | Secure, internet-free access from VPC to DynamoDB |
| 59 | How Elastic Beanstalk operates EC2 instances | Uses ASG and ALB for launching, health checking, and versioning. |
| 60 | IAM Access Analyzer | Detects public or cross-account access using resource-based policies. |
| 61 | IAM Authorization with SigV4 & API GW | Use **SigV4-signed requests** for **IAM-based auth** in API Gateway (`AWS_IAM`). Great for service-to-service. Not suitable for public apps. |
| 62 | IAM credential types for CodeCommit | Supports SSH keys, Git credentials, and AWS access keys. |
| 63 | Immediate forecast if usage exists | Forecast available immediately if 5+ weeks of prior data exists. |
| 64 | Invalidate API Gateway Cache | Send `Cache-Control: max-age=0` to bypass API Gateway cache |
| 65 | KMS direct encryption behavior | Up to 4 KB data can be encrypted directly; uses envelope encryption for larger data. |
| 66 | KMS encryption process | KMS stores CMKs and encrypts client data internally. |
| 67 | Lambda Authorizer vs Cognito User Pools | Lambda for custom auth logic; Cognito for managed user auth. |
| 68 | Lambda Package Size Limits | Max 50MB zipped (CLI), 250MB unzipped (via S3), 5x50MB for layers |
| 69 | MOCK Integrations in API Gateway | Returns predefined responses with no backend |
| 70 | Origin Group in CloudFront | Ensures failover between two origins in CloudFront |
| 71 | Public APIs with API Keys | Use **API Keys** in API Gateway to **identify and throttle** access from known clients (web, mobile). Combine with Lambda authorizer for better validation. |
| 72 | RCU and WCU in DynamoDB | Defines throughput for read/write operations |
| 73 | Redis Cluster and Cluster Mode | Cluster mode enables sharding, HA; cluster-aware client required |
| 74 | S3 CLI: Pagination Options | Use `--max-items` (limit total returned), `--page-size` (items per API call), `--starting-token` (resume pagination). All useful for **efficient batch processing**. |
| 75 | S3 Event Notifications to SNS | Trigger SNS topic when an object is uploaded to S3 |
| 76 | S3 Replication (SRR/CRR) | Auto-copy of objects within or across AWS regions |
| 77 | S3 Select | Allows querying a **subset of data** from S3 objects using **SQL-like expressions**. Reduces data transfer and processing costs. Supports CSV, JSON, and Parquet. |
| 78 | S3 Versioning & Null Version | Objects uploaded before versioning have a `null` version ID. Uploads after enabling versioning get unique IDs. After a delete, a **delete marker** is created with its own version ID. |
| 79 | SNS Filter Policy | Controls message delivery to subscribers using message attributes. |
| 80 | SNS Subscription | Defines endpoint and protocol for receiving messages from topic. |
| 81 | SNS Topic | Core component to publish messages to multiple subscribers. |
| 82 | SQS Dead-Letter Queues (DLQ) | Captures messages that fail processing after max retry attempts |
| 83 | SQS Extended Client | Stores large payloads in S3, only references in SQS |
| 84 | SQS FIFO Options | Use `MessageGroupId` (required), `MessageDeduplicationId`, or `ContentBasedDeduplication` to ensure **strict ordering** and **exactly-once processing** in FIFO queues. |
| 85 | SQS: MessageGroupId in Standard Queue | `MessageGroupId` is **only supported in FIFO queues**. Standard queues do not guarantee order or support this field. Attempting to use it causes a validation error. |
| 86 | SSE-C and S3 + HTTP Restriction | SSE-C requires HTTPS; HTTP requests are rejected |
| 87 | SSE-S3 Costs and Limitations | Free, low-latency, but not reusable for other services |
| 88 | SSM SecureString for Secrets | Store secrets using encrypted parameters in SSM |
| 89 | STS Service Responsibilities | Temporary creds, role assumption, error decoding |
| 90 | Send Data to Kinesis from EC2 | Use SDK, CLI, Kinesis Agent, or KPL depending on source |
| 91 | Shared Volume (EFS) | EFS allows concurrent mounts from multiple EC2s across AZs. |
| 92 | Stack vs Subnet Concepts in CloudFormation | Understand stack structure and how subnets fit into CFN definitions |
| 93 | Standard CloudWatch EC2 Metrics | Includes CPU, network, disk metrics; excludes memory |
| 94 | Step Functions Workflow Types | Standard = durable, Express = high-speed |
| 95 | Subnet Logs | No standalone logs; use VPC Flow Logs at the subnet level. |
| 96 | Triggering Beanstalk Workers | Works only with SQS, not direct events or HTTP |
| 97 | VPC Flow Logs | Captures IP-level metadata for VPC/Subnet/ENI traffic. |
| 98 | VPN Logs | Monitor tunnel status and client connection logs via CloudWatch. |
| 99 | X-Ray Annotations & Indexes | Use **Annotations** (simple key-value pairs) for **filtering** and **grouping traces** in X-Ray; searchable types: `string`, `number`, `boolean`. Metadata is **not indexed** and used for debugging only. |
| 100 | X-Ray Sampling Feature | Controls which requests are traced to manage cost and detail. |
| 101 | CloudFront: Cognito Integration Limitation | CloudFront does not natively support Cognito authentication. |
| 102 | CloudFront: Origin Group Failover | Only one primary and one secondary origin per group; not load-balanced. |
| 103 | CodeDeploy: Deployment Configurations | Controls deployment speed (AllAtOnce, HalfAtATime, OneAtATime). |
| 104 | CodeDeploy: Deployment Group | Defines where and how deployments occur; can target EC2, Lambda, or ECS. |
| 105 | CodeDeploy: Rollback and Hooks | Supports lifecycle events, alarm-based rollbacks, and load balancer integration. |
| 106 | DynamoDB: Conflict Handling in Global Tables | Last writer wins (based on timestamp); replication is asynchronous. |
| 107 | DynamoDB: Global Tables for Global Users | Use Global Tables to reduce latency for globally distributed users. |
| 108 | EBS: CreateVolume Not in CloudTrail (EC2 launch) | EBS volumes created during EC2 launch won’t log `CreateVolume` in CT. |
| 109 | EBS: Region-Wide Encryption by Default | Cannot turn off encryption per volume once default is enabled. |
| 110 | EC2: Multi-AZ RDS | Provides automatic failover and high availability via standby instance. |
| 111 | ECR: `get-login --no-include-email` | Authenticates Docker to ECR; now deprecated in favor of `get-login-password`. |
| 112 | IAM Policy: `"Resource": "*"` Meaning | Grants permissions for all resources; used when targets are dynamic. |
| 113 | RDS vs Read Replicas | Multi-AZ is for HA, Read Replicas are for scalability (read traffic). |
| 114 | S3: CloudFront Signed URLs/Cookies | Used to restrict access to S3 via CloudFront; not related to Cognito. |
| 115 | S3: Encryption by Default | Region-wide setting; can't disable encryption for individual resources. |
| 116 | S3: Eventual Consistency on Bucket Deletion | Deleted bucket might still appear due to eventual consistency. |
| 117 | S3: Simultaneous Writes & Event Notifications | Simultaneous writes to non-versioned object may trigger only one event. |
| 118 | SQS: Max Number of Messages | You can retrieve up to 10 messages in a single `ReceiveMessage` call. |
| 119 | STS: Role Assumption by API Gateway | API Gateway uses STS to assume an IAM role for CloudWatch logging. |
| 120 | STS: Why It’s Needed | Used to get temporary credentials to write logs securely. |
| 121 | `appspec.yml` vs `buildspec.yml` | `appspec.yml` is for CodeDeploy deployments; `buildspec.yml` is for CodeBuild builds. |
| 122 | `cdk deploy` | Synthesizes and deploys a CDK app to AWS via CloudFormation. |
| 123 | `cdk diff` | Compares local CDK app with deployed stack to preview changes. |
| 124 | `sam deploy` | Performs a full CloudFormation stack deployment from a SAM app. |
| 125 | `sam sync` | Rapidly updates code/config for existing resources, but cannot create new ones. |
| 126 | ecs.config File | Controls ECS agent behavior on EC2 instances |
