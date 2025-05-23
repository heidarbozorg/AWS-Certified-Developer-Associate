# AWS Certified Developer – Associate Last Dates Notes

## Cheat Sheet Table

| # | Topic | Summary |
|----|-------|---------|
| 1  | [ALB Host-Based vs Path-Based Routing](#1-alb-host-based-vs-path-based-routing) | Route based on domain (host-header) or URL path (path-pattern) |
| 2  | [ALB Target Types (Instance, IP, Lambda)](#2-alb-target-types-instance-ip-lambda) | ALB can route to EC2, IPs, or Lambda with different behaviors |
| 3  | [ASG Detailed Monitoring](#3-asg-detailed-monitoring) | Enables 1-min metrics for faster auto scaling |
| 4  | [AWS Budget Forecasting Delay](#4-aws-budget-forecasting-delay) | Requires ~5 weeks of usage data to generate forecast. |
| 5  | [AWS CDK App Template](#5-aws-cdk-app-template) | Generates project structure for defining infrastructure as code. |
| 6  | [AWS CLI `--dry-run`](#6-aws-cli-dry-run) | Tests IAM permissions for an action without actually executing it. |
| 7  | [AWS CloudFormation Change Sets](#7-aws-cloudformation-change-sets) | Previews changes to resources before applying an update |
| 8  | [AWS CodeStar](#8-aws-codestar) | All-in-one UI for CI/CD with CodeCommit, CodeBuild, CodePipeline, CodeDeploy |
| 9  | [AWS Glue](#9-aws-glue) | Discover, catalog, and transform data using visual or code jobs |
| 10 | [AWS KMS: Data Key Caching](#10-aws-kms-data-key-caching) | Reduces KMS calls using SDK-level data key caching with TTL and limits |
| 11 | [AWS Serverless Application Repository (SAR)](#11-aws-serverless-application-repository-sar) | Repository of reusable serverless apps built with AWS SAM. |
| 12 | [Access Control List (ACL) vs Trust Policy](#12-access-control-list-acl-vs-trust-policy) | ACLs manage resource access; trust policies define who can assume a role. |
| 13 | [Amazon EFS in ECS Fargate across AZs](#13-amazon-efs-in-ecs-fargate-across-azs) | EFS must have mount targets in all AZs for multi-AZ Fargate tasks. |
| 14 | [Amazon Macie](#14-amazon-macie) | ML-powered S3 scanning for PII and sensitive data. Outputs findings, not enforcement. |
| 15 | [Auto Scaling Group across Regions](#15-auto-scaling-group-across-regions) | ASGs are regional; cross-region scaling requires multiple ASGs. |
| 16 | [BGP Logs](#16-bgp-logs) | Logs for dynamic VPN routing behavior; visible via DescribeVpnConnections. |
| 17 | [Backlog per Instance Metric in ECS with SQS](#17-backlog-per-instance-metric-in-ecs-with-sqs) | Scales ECS tasks based on SQS messages divided by running tasks. |
| 18 | [Batch Operations in DynamoDB](#18-batch-operations-in-dynamodb) | Reduce API calls by grouping reads/writes |
| 19 | [Beanstalk Docker & Custom Platforms](#19-beanstalk-docker--custom-platforms) | Use `Dockerrun.aws.json` (v1/v2) for Docker; Packer for custom platforms. |
| 20 | [Beanstalk Worker & `cron.yaml`](#20-beanstalk-worker--cronyaml) | Define scheduled jobs in Beanstalk Worker with `cron.yaml`. |
| 21 | [Beanstalk vs Lambda for SQS](#21-beanstalk-vs-lambda-for-sqs) | Choose based on latency, cost, and flexibility |
| 22 | [Beanstalk: Rolling with Additional Batch](#22-beanstalk-rolling-with-additional-batch) | Deployment strategy that **adds a temporary batch of instances** during updates, ensuring **no downtime**. Great for production apps needing high availability. |
| 23 | [Built-in Encryption in S3](#23-built-in-encryption-in-s3) | Uses SSE-S3, SSE-KMS, or SSE-C to encrypt objects at rest |
| 24 | [CDK does not generate application code](#24-cdk-does-not-generate-application-code) | CDK defines infrastructure; you write app code like Lambda separately. |
| 25 | [CFN Parameter Type – `AWS::EC2::KeyPair::KeyName`](#25-cfn-parameter-type--awsec2keypairkeyname) | Ensures user selects a valid EC2 KeyPair for SSH access. |
| 26 | [CloudFormation CLI Commands](#26-cloudformation-cli-commands) | Use `package`, `deploy`, `create-stack`, etc. |
| 27 | [CloudFormation Import/Export Syntax](#27-cloudformation-importexport-syntax) | Use `Export`/`Fn::ImportValue` to share values across stacks |
| 28 | [CloudFormation Parameter Types](#28-cloudformation-parameter-types) | Includes basic types (String, Number) and AWS-specific resource types. |
| 29 | [CloudFormation Pseudo Parameters](#29-cloudformation-pseudo-parameters) | Built-in variables like AWS::AccountId or AWS::Region |
| 30 | [CloudFront Key Pairs - Root User](#30-cloudfront-key-pairs---root-user) | Only root can create CloudFront key pairs for signed URLs. |
| 31 | [CloudTrail and S3 Object Ownership](#31-cloudtrail-and-s3-object-ownership) | Logging only works if bucket owner also owns the object |
| 32 | [CloudWatch Logs Encryption via KMS](#32-cloudwatch-logs-encryption-via-kms) | Associate CMK with log group and grant access |
| 33 | [CodeDeploy Lifecycle Hooks (In-Place)](#33-codedeploy-lifecycle-hooks-in-place) | Six ordered hooks like ApplicationStop, BeforeInstall, etc. |
| 34 | [Cognito Sync](#34-cognito-sync) | Deprecated feature for cross-device data sync |
| 35 | [DAX in DynamoDB](#35-dax-in-dynamodb) | In-memory cache for fast, low-latency reads |
| 36 | [Dedicated Worker in Beanstalk](#36-dedicated-worker-in-beanstalk) | Processes SQS messages using EC2-based app |
| 37 | [DynamoDB GSIs and LSIs](#37-dynamodb-gsis-and-lsis) | GSIs allow alternate PK/SK; LSIs allow alternate SK only |
| 38 | [DynamoDB On-Demand Backups](#38-dynamodb-on-demand-backups) | Manual full-table backups, stored in AWS-managed S3 (no direct access). |
| 39 | [DynamoDB Point-in-Time Recovery (PITR)](#39-dynamodb-point-in-time-recovery-pitr) | Automatically backs up data with second-level recovery up to 35 days. |
| 40 | [DynamoDB Pricing](#40-dynamodb-pricing) | Charges for storage, RCU/WCU, and optional features |
| 41 | [EBS AZ Locking](#41-ebs-az-locking) | EBS volumes are locked to a single Availability Zone. |
| 42 | [EBS Cross-Region Restore](#42-ebs-cross-region-restore) | Snapshot → copy snapshot to another region → create new volume. |
| 43 | [EBS Multi-Attach](#43-ebs-multi-attach) | `io1/io2` volumes support multi-attach to EC2 in the same AZ. |
| 44 | [EC2 Auto Scaling – ALBRequestCountPerTarget](#44-ec2-auto-scaling--albrequestcountpertarget) | Scales based on number of incoming ALB requests per instance. |
| 45 | [EC2 Auto Scaling – ASGAverageCPUUtilization](#45-ec2-auto-scaling--asgaveragecpuutilization) | Average CPU usage across ASG; commonly used in target tracking. |
| 46 | [EC2 Auto Scaling – ASGAverageNetworkOut](#46-ec2-auto-scaling--asgaveragenetworkout) | Scales based on outbound network traffic from instances. |
| 47 | [EC2 Instance Metadata](#47-ec2-instance-metadata) | Access instance details from `169.254.169.254`; use IMDSv2 for security. |
| 48 | [EC2 Reserved Instances (Regional)](#48-ec2-reserved-instances-regional) | Regional RIs offer cost savings without capacity reservation. |
| 49 | [EC2 Reserved Instances (Zonal)](#49-ec2-reserved-instances-zonal) | Zonal RIs include capacity reservation and are AZ-specific. |
| 50 | [ElastiCache: Redis vs Memcached](#50-elasticache-redis-vs-memcached) | Use Redis for durability & structure; Memcached for speed & simplicity |
| 51 | [Elastic Beanstalk Instance Recovery](#51-elastic-beanstalk-instance-recovery) | Replaces failed instances with last successful app version. |
| 52 | [Elastic Beanstalk Serverless?](#52-elastic-beanstalk-serverless) | Not serverless—manages EC2 with auto scaling |
| 53 | [Ephemeral Ports in EC2/ELB Communication](#53-ephemeral-ports-in-ec2elb-communication) | EC2 responds on ports 1024–65535; important for firewalls & NACLs |
| 54 | [EventBridge (CloudWatch Events) Rules](#54-eventbridge-cloudwatch-events-rules) | Trigger Lambda, Step Functions, etc. based on events or schedule |
| 55 | [Export DynamoDB with Data Pipeline](#55-export-dynamodb-with-data-pipeline) | Scheduled DynamoDB table export to S3 (even cross-account). |
| 56 | [Export DynamoDB with EMR (Hive)](#56-export-dynamodb-with-emr-hive) | Use Hive on EMR to query/export DynamoDB data to S3. |
| 57 | [Export DynamoDB with Glue](#57-export-dynamodb-with-glue) | ETL from DynamoDB to S3 using AWS Glue jobs; downloadable data. |
| 58 | [Gateway VPC Endpoint for DynamoDB](#58-gateway-vpc-endpoint-for-dynamodb) | Secure, internet-free access from VPC to DynamoDB |
| 59 | [How Elastic Beanstalk operates EC2 instances](#59-how-elastic-beanstalk-operates-ec2-instances) | Uses ASG and ALB for launching, health checking, and versioning. |
| 60 | [IAM Access Analyzer](#60-iam-access-analyzer) | Detects public or cross-account access using resource-based policies. |
| 61 | [IAM Authorization with SigV4 & API GW](#61-iam-authorization-with-sigv4--api-gw) | Use **SigV4-signed requests** for **IAM-based auth** in API Gateway (`AWS_IAM`). Great for service-to-service. Not suitable for public apps. |
| 62 | [IAM credential types for CodeCommit](#62-iam-credential-types-for-codecommit) | Supports SSH keys, Git credentials, and AWS access keys. |
| 63 | [Immediate forecast if usage exists](#63-immediate-forecast-if-usage-exists) | Forecast available immediately if 5+ weeks of prior data exists. |
| 64 | [Invalidate API Gateway Cache](#64-invalidate-api-gateway-cache) | Send `Cache-Control: max-age=0` to bypass API Gateway cache |
| 65 | [KMS direct encryption behavior](#65-kms-direct-encryption-behavior) | Up to 4 KB data can be encrypted directly; uses envelope encryption for larger data. |
| 66 | [KMS encryption process](#66-kms-encryption-process) | KMS stores CMKs and encrypts client data internally. |
| 67 | [Lambda Authorizer vs Cognito User Pools](#67-lambda-authorizer-vs-cognito-user-pools) | Lambda for custom auth logic; Cognito for managed user auth. |
| 68 | [Lambda Package Size Limits](#68-lambda-package-size-limits) | Max 50MB zipped (CLI), 250MB unzipped (via S3), 5x50MB for layers |
| 69 | [MOCK Integrations in API Gateway](#69-mock-integrations-in-api-gateway) | Returns predefined responses with no backend |
| 70 | [Origin Group in CloudFront](#70-origin-group-in-cloudfront) | Ensures failover between two origins in CloudFront |
| 71 | [Public APIs with API Keys](#71-public-apis-with-api-keys) | Use **API Keys** in API Gateway to **identify and throttle** access from known clients (web, mobile). Combine with Lambda authorizer for better validation. |
| 72 | [RCU and WCU in DynamoDB](#72-rcu-and-wcu-in-dynamodb) | Defines throughput for read/write operations |
| 73 | [Redis Cluster and Cluster Mode](#73-redis-cluster-and-cluster-mode) | Cluster mode enables sharding, HA; cluster-aware client required |
| 74 | [S3 CLI: Pagination Options](#74-s3-cli-pagination-options) | Use `--max-items`, `--page-size`, `--starting-token` for batch processing |
| 75 | [S3 Event Notifications to SNS](#75-s3-event-notifications-to-sns) | Trigger SNS topic when an object is uploaded to S3 |
| 76 | [S3 Replication (SRR/CRR)](#76-s3-replication-srrcrr) | Auto-copy of objects within or across AWS regions |
| 77 | [S3 Select](#77-s3-select) | Query subset of S3 object data using SQL-like expressions |
| 78 | [S3 Versioning & Null Version](#78-s3-versioning--null-version) | Tracks object versions; delete creates a marker |
| 79 | [SNS Filter Policy](#79-sns-filter-policy) | Controls message delivery to subscribers using message attributes. |
| 80 | [SNS Subscription](#80-sns-subscription) | Defines endpoint and protocol for receiving messages from topic. |
| 81 | [SNS Topic](#81-sns-topic) | Core component to publish messages to multiple subscribers. |
| 82 | [SQS Dead-Letter Queues (DLQ)](#82-sqs-dead-letter-queues-dlq) | Captures messages that fail processing after max retry attempts |
| 83 | [SQS Extended Client](#83-sqs-extended-client) | Stores large payloads in S3, only references in SQS |
| 84 | [SQS FIFO Options](#84-sqs-fifo-options) | Use `MessageGroupId`, `MessageDeduplicationId`, etc. for ordering |
| 85 | [SQS: MessageGroupId in Standard Queue](#85-sqs-messagegroupid-in-standard-queue) | Only valid for FIFO queues; standard queues don’t support it |
| 86 | [SSE-C and S3 + HTTP Restriction](#86-sse-c-and-s3--http-restriction) | SSE-C requires HTTPS; HTTP requests are rejected |
| 87 | [SSE-S3 Costs and Limitations](#87-sse-s3-costs-and-limitations) | Free, low-latency, but not reusable for other services |
| 88 | [SSM SecureString for Secrets](#88-ssm-securestring-for-secrets) | Store secrets using encrypted parameters in SSM |
| 89 | [STS Service Responsibilities](#89-sts-service-responsibilities) | Temporary creds, role assumption, error decoding |
| 90 | [Send Data to Kinesis from EC2](#90-send-data-to-kinesis-from-ec2) | Use SDK, CLI, Kinesis Agent, or KPL depending on source |
| 91  | [Shared Volume (EFS)](#91-shared-volume-efs) | EFS allows concurrent mounts from multiple EC2s across AZs. |
| 92  | [Stack vs Subnet Concepts in CloudFormation](#92-stack-vs-subnet-concepts-in-cloudformation) | Understand stack structure and how subnets fit into CFN definitions |
| 93  | [Standard CloudWatch EC2 Metrics](#93-standard-cloudwatch-ec2-metrics) | Includes CPU, network, disk metrics; excludes memory |
| 94  | [Step Functions Workflow Types](#94-step-functions-workflow-types) | Standard = durable, Express = high-speed |
| 95  | [Subnet Logs](#95-subnet-logs) | No standalone logs; use VPC Flow Logs at the subnet level. |
| 96  | [Triggering Beanstalk Workers](#96-triggering-beanstalk-workers) | Works only with SQS, not direct events or HTTP |
| 97  | [VPC Flow Logs](#97-vpc-flow-logs) | Captures IP-level metadata for VPC/Subnet/ENI traffic. |
| 98  | [VPN Logs](#98-vpn-logs) | Monitor tunnel status and client connection logs via CloudWatch. |
| 99  | [X-Ray Annotations & Indexes](#99-x-ray-annotations--indexes) | Use annotations to group/filter traces; metadata not indexed |
| 100 | [X-Ray Sampling Feature](#100-x-ray-sampling-feature) | Controls which requests are traced to manage cost and detail. |
| 101 | [CloudFront: Cognito Integration Limitation](#101-cloudfront-cognito-integration-limitation) | CloudFront does not natively support Cognito authentication. |
| 102 | [CloudFront: Origin Group Failover](#102-cloudfront-origin-group-failover) | Only one primary and one secondary origin per group; not load-balanced. |
| 103 | [CodeDeploy: Deployment Configurations](#103-codedeploy-deployment-configurations) | Controls deployment speed (AllAtOnce, HalfAtATime, OneAtATime). |
| 104 | [CodeDeploy: Deployment Group](#104-codedeploy-deployment-group) | Defines where and how deployments occur; can target EC2, Lambda, or ECS. |
| 105 | [CodeDeploy: Rollback and Hooks](#105-codedeploy-rollback-and-hooks) | Supports lifecycle events, alarm-based rollbacks, and load balancer integration. |
| 106 | [DynamoDB: Conflict Handling in Global Tables](#106-dynamodb-conflict-handling-in-global-tables) | Last writer wins (based on timestamp); replication is asynchronous. |
| 107 | [DynamoDB: Global Tables for Global Users](#107-dynamodb-global-tables-for-global-users) | Use Global Tables to reduce latency for globally distributed users. |
| 108 | [EBS: CreateVolume Not in CloudTrail (EC2 launch)](#108-ebs-createvolume-not-in-cloudtrail-ec2-launch) | EBS volumes created during EC2 launch won’t log `CreateVolume` in CT. |
| 109 | [EBS: Region-Wide Encryption by Default](#109-ebs-region-wide-encryption-by-default) | Cannot turn off encryption per volume once default is enabled. |
| 110 | [EC2: Multi-AZ RDS](#110-ec2-multi-az-rds) | Provides automatic failover and high availability via standby instance. |
| 111 | [ECR: `get-login --no-include-email`](#111-ecr-get-login---no-include-email) | Authenticates Docker to ECR; now deprecated in favor of `get-login-password`. |
| 112 | [IAM Policy: "Resource": "*" Meaning](#112-iam-policy-resource--meaning) | Grants permissions for all resources; used when targets are dynamic. |
| 113 | [RDS vs Read Replicas](#113-rds-vs-read-replicas) | Multi-AZ is for HA, Read Replicas are for scalability (read traffic). |
| 114 | [S3: CloudFront Signed URLs/Cookies](#114-s3-cloudfront-signed-urlsCookies) | Used to restrict access to S3 via CloudFront; not related to Cognito. |
| 115 | [S3: Encryption by Default](#115-s3-encryption-by-default) | Region-wide setting; can't disable encryption for individual resources. |
| 116 | [S3: Eventual Consistency on Bucket Deletion](#116-s3-eventual-consistency-on-bucket-deletion) | Deleted bucket might still appear due to eventual consistency. |
| 117 | [S3: Simultaneous Writes & Event Notifications](#117-s3-simultaneous-writes--event-notifications) | Simultaneous writes to non-versioned object may trigger only one event. |
| 118 | [SQS: Max Number of Messages](#118-sqs-max-number-of-messages) | You can retrieve up to 10 messages in a single ReceiveMessage call. |
| 119 | [STS: Role Assumption by API Gateway](#119-sts-role-assumption-by-api-gateway) | API Gateway uses STS to assume an IAM role for CloudWatch logging. |
| 120 | [STS: Why It’s Needed](#120-sts-why-its-needed) | Used to get temporary credentials to write logs securely. |
| 121 | [`appspec.yml` vs `buildspec.yml`](#121-appspecyml-vs-buildspecyml) | `appspec.yml` is for CodeDeploy deployments; `buildspec.yml` is for CodeBuild builds. |
| 122 | [`cdk deploy`](#122-cdk-deploy) | Synthesizes and deploys a CDK app to AWS via CloudFormation. |
| 123 | [`cdk diff`](#123-cdk-diff) | Compares local CDK app with deployed stack to preview changes. |
| 124 | [`sam deploy`](#124-sam-deploy) | Performs a full CloudFormation stack deployment from a SAM app. |
| 125 | [`sam sync`](#125-sam-sync) | Rapidly updates code/config for existing resources, but cannot create new ones. |
| 126 | [ecs.config File](#126-ecsconfig-file) | Controls ECS agent behavior on EC2 instances |

---

## Detailed Notes

### 1. ALB Host-Based vs Path-Based Routing
Application Load Balancer (ALB) supports routing based on **host headers** (e.g., `api.example.com`) or **path patterns** (e.g., `/images/*`). Use host-based routing to serve multiple domains from one ALB, and path-based routing to forward requests to different target groups based on URL structure.

### 2. ALB Target Types (Instance, IP, Lambda)
ALBs can forward traffic to:
- **Instances** registered with EC2.
- **IP addresses**, including on-premises or container IPs.
- **Lambda functions**, enabling serverless application load balancing.
Each type has specific considerations for scaling, availability, and integration.

### 3. ASG Detailed Monitoring
Auto Scaling Groups (ASGs) by default use 5-minute CloudWatch metrics. Enabling **detailed monitoring** provides **1-minute metrics**, which allows faster detection of changes and triggers more responsive scaling actions.

### 4. AWS Budget Forecasting Delay
The AWS Budgets forecasting feature uses historical usage data to predict future costs. Forecasts typically require **4–5 weeks** of usage history to generate reliable projections, especially for newly created budgets.

### 5. AWS CDK App Template
Running `cdk init app --language typescript` (or other language) bootstraps an AWS CDK project with a ready-to-use structure. This includes a stack definition, dependencies, and build setup to start defining infrastructure as code right away.

### 6. AWS CLI `--dry-run`
Many AWS CLI commands support the `--dry-run` flag, which checks whether the action could be performed, based on current IAM permissions, without making any changes. Useful for verifying role permissions before executing real operations.

### 7. AWS CloudFormation Change Sets
Change Sets in AWS CloudFormation allow you to preview changes (additions, modifications, deletions) that a stack update will make—before executing the update. This helps avoid unintentional disruptions or costs due to misconfigured templates.

### 8. AWS CodeStar
AWS CodeStar offers a unified dashboard to manage the full CI/CD lifecycle. It integrates with CodeCommit (source), CodeBuild (build), CodeDeploy (deploy), and CodePipeline (automation). Ideal for quick team onboarding and consistent DevOps practices.

### 9. AWS Glue
AWS Glue is a managed ETL (Extract, Transform, Load) service. It can **crawl** data sources to create a catalog, and you can build **visual or code-based jobs** to clean and transform data across formats like CSV, JSON, or Parquet.

### 10. AWS KMS: Data Key Caching
Using **data key caching** in the AWS Encryption SDK allows applications to reuse decrypted data keys stored in memory. This reduces **AWS KMS API calls**, lowering cost and latency. Cache entries respect TTL and usage caps to maintain security.

### 11. AWS Serverless Application Repository (SAR)
The AWS Serverless Application Repository is a collection of vetted, reusable serverless applications that you can deploy directly into your account. Apps are built with AWS SAM and can be shared publicly or privately within your organization.

### 12. Access Control List (ACL) vs Trust Policy
- **ACLs** manage access to resources (like S3 objects) by specifying who can do what.
- **Trust policies** are part of IAM roles and define **who is allowed to assume the role**, such as a federated user or AWS service.

### 13. Amazon EFS in ECS Fargate across AZs
When using **Amazon EFS** with **ECS on Fargate** in a multi-AZ setup, EFS must have **mount targets in each Availability Zone** where Fargate tasks will run. Otherwise, tasks in AZs without mount targets will fail to access the filesystem.

### 14. Amazon Macie
Amazon Macie uses **machine learning** to scan your S3 buckets for **PII** and other sensitive data types. It provides **findings** (detection reports), but does not block or encrypt data. Useful for **compliance auditing** and **data classification**.

### 15. Auto Scaling Group across Regions
Auto Scaling Groups (ASGs) are **region-scoped** AWS resources. To achieve cross-region scaling or redundancy, you must create separate ASGs in each region and handle coordination via CloudWatch, Lambda, or third-party tools.

### 16. BGP Logs
For **dynamic VPN connections** using BGP (Border Gateway Protocol), AWS provides **route logs** viewable through `DescribeVpnConnections`. These logs help you troubleshoot route advertisements and VPN status.

### 17. Backlog per Instance Metric in ECS with SQS
A common ECS + SQS scaling strategy uses the **Backlog per Instance** metric: ApproximateNumberOfMessagesVisible / DesiredTaskCount. This helps auto scale ECS services based on the number of SQS messages each task should handle.

### 18. Batch Operations in DynamoDB
DynamoDB supports **batch operations** like `BatchGetItem` and `BatchWriteItem`, allowing you to group multiple reads/writes in a single request. This improves efficiency and reduces API cost, but has limits (e.g., 25 items max per batch write).

### 19. Beanstalk Docker & Custom Platforms
Elastic Beanstalk supports:
- **Single-container Docker** via `Dockerrun.aws.json` v1
- **Multi-container Docker** using ECS via `Dockerrun.aws.json` v2
- **Custom platforms**, where you create your own AMI using Packer for full environment control

### 20. Beanstalk Worker & `cron.yaml`
In a **Worker environment**, you can schedule recurring jobs using `cron.yaml`. The file defines cron expressions (UTC-based) and target paths. Beanstalk sends HTTP POST requests to the defined route at the scheduled times.

### 21. Beanstalk vs Lambda for SQS
Use **Lambda** for lightweight, low-latency SQS processing with pay-per-use pricing and high concurrency. Use **Elastic Beanstalk** for complex workflows, longer tasks, or when you need access to an entire EC2 environment with full control.

### 22. Beanstalk: Rolling with Additional Batch
This deployment strategy temporarily **adds new instances** alongside the existing ones during an update, performs deployment on the new batch, and only then removes the old batch. It **avoids downtime**, ideal for production systems needing high availability.

### 23. Built-in Encryption in S3
S3 supports built-in encryption at rest using:
- **SSE-S3**: Managed by AWS.
- **SSE-KMS**: Uses AWS Key Management Service for additional audit control.
- **SSE-C**: You manage your own keys.

### 24. CDK does not generate application code
The AWS CDK helps you define **infrastructure as code** (like Lambda functions, APIs, etc.), but **does not generate application logic**. You must write your app code separately and reference it in your CDK constructs (e.g., by path or asset).

### 25. CFN Parameter Type – `AWS::EC2::KeyPair::KeyName`
When defining CloudFormation templates, using this parameter type ensures that users select from a list of **valid EC2 Key Pairs** in the region. It’s typically used to enable SSH access to instances launched by the template.

### 26. CloudFormation CLI Commands
Important AWS CLI commands for managing CloudFormation stacks include:
- `package`: Prepares code/resources for deployment (e.g., uploads Lambda).
- `deploy`: Applies the stack.
- `create-stack`, `update-stack`: Manually control stack lifecycle.

### 27. CloudFormation Import/Export Syntax
To share values (e.g., VPC IDs, subnet IDs) between stacks:
- Use `Export` in the first stack to name an output.
- Use `Fn::ImportValue` in the second stack to reference it.

### 28. CloudFormation Parameter Types
CloudFormation supports:
- **Basic types**: String, Number, CommaDelimitedList
- **AWS-specific types**: AWS::EC2::Subnet::Id, AWS::SSM::Parameter::Value<String>, etc.
These help validate inputs and enable dropdowns in the console UI.

### 29. CloudFormation Pseudo Parameters
These are **built-in variables** available in any CloudFormation template, including:
- `AWS::AccountId`
- `AWS::Region`
- `AWS::StackName`
- `AWS::Partition`

They’re useful for dynamic referencing within templates.

### 30. CloudFront Key Pairs - Root User
To sign URLs for private CloudFront distributions using **key pairs**, you must use a key pair created by the **root account**. IAM users and roles cannot manage or use CloudFront key pairs—this is a restriction for security and access control.

### 31. CloudTrail and S3 Object Ownership
For CloudTrail to log S3 object-level actions, the **bucket owner must also own the object** being accessed. If an external account uploads an object and retains ownership, CloudTrail may not log access to that object unless ownership is granted or changed.

### 32. CloudWatch Logs Encryption via KMS
You can encrypt CloudWatch Logs with a **customer-managed KMS key (CMK)** by associating the key with a log group. Ensure that the necessary IAM permissions (`kms:Encrypt`, `kms:Decrypt`, etc.) are granted to the log group and any accessing services.

### 33. CodeDeploy Lifecycle Hooks (In-Place)
AWS CodeDeploy’s **in-place deployments** use the following lifecycle hooks:
1. `ApplicationStop`
2. `BeforeInstall`
3. `AfterInstall`
4. `ApplicationStart`
5. `ValidateService`
6. `BeforeAllowTraffic` / `AfterAllowTraffic` (only with traffic shifting)
Hooks are defined in `appspec.yml` and can run scripts or commands on EC2 instances.

### 34. Cognito Sync
**Amazon Cognito Sync** was a legacy service for syncing user profile data across devices. It is now **deprecated**, and users should use **AWS AppSync or Amazon Cognito + DynamoDB** for multi-device data sync scenarios.

### 35. DAX in DynamoDB
**DynamoDB Accelerator (DAX)** is a **fully managed, in-memory cache** that improves read performance to **microsecond latency**. It supports eventual consistency and is ideal for **read-heavy** workloads needing extreme speed.

### 36. Dedicated Worker in Beanstalk
In Elastic Beanstalk, a **Worker environment** with a **dedicated EC2 app** processes incoming SQS messages. You define the processing logic, and Beanstalk takes care of polling SQS and triggering your app via HTTP POST.

### 37. DynamoDB GSIs and LSIs
- **GSI (Global Secondary Index)**: Enables querying on alternate **Partition and Sort Keys**, stored independently.
- **LSI (Local Secondary Index)**: Shares the same Partition Key as the main table, but allows querying on different **Sort Keys**.
LSIs are created during table creation; GSIs can be added later.

### 38. DynamoDB On-Demand Backups
With on-demand backups, you can manually trigger **full-table backups** at any time. These are stored in AWS-managed storage (e.g., S3 under the hood), but are **not directly accessible** — only restorable into a new table.

### 39. DynamoDB Point-in-Time Recovery (PITR)
PITR automatically backs up your DynamoDB table continuously and allows recovery to any **second-level point** within the past **35 days**. It complements on-demand backups and is useful for accidental writes or deletes.

### 40. DynamoDB Pricing
DynamoDB pricing includes:
- **Data storage** (per GB)
- **Read/Write Capacity Units (RCU/WCU)** or **On-Demand capacity**
- **Optional features** like PITR, DAX, Streams, and Global Tables
Each adds cost depending on your use case and configuration.

### 41. EBS AZ Locking
Amazon EBS volumes are tied to a **single Availability Zone**. You cannot attach an EBS volume to an EC2 instance in a different AZ. To move data across AZs, create a snapshot and restore it in the target zone.

### 42. EBS Cross-Region Restore
To restore an EBS volume in another region:
1. Create a **snapshot** of the source volume.
2. **Copy** the snapshot to the target region.
3. Create a **new volume** from the copied snapshot in that region.

### 43. EBS Multi-Attach
EBS **`io1` and `io2`** volume types support **Multi-Attach**, allowing the same volume to be attached to multiple EC2 instances within the **same Availability Zone**. Requires coordination via a cluster-aware file system.

### 44. EC2 Auto Scaling – ALBRequestCountPerTarget
This scaling policy uses **ALB metrics** to scale based on the **number of requests per target** in a target group. Useful for web applications where request volume per instance is a bottleneck.

### 45. EC2 Auto Scaling – ASGAverageCPUUtilization
This is a common **target tracking policy** that scales an Auto Scaling Group to maintain a target **average CPU usage** across all instances, e.g., scale out when above 70%.

### 46. EC2 Auto Scaling – ASGAverageNetworkOut
This scaling policy tracks **average network output (in bytes)** per instance in the Auto Scaling Group. It's useful for applications like video streaming or file transfers with heavy outbound traffic.

### 47. EC2 Instance Metadata
You can query **instance metadata** using `http://169.254.169.254/latest/meta-data/` to retrieve details like instance ID, IP addresses, and security groups. **IMDSv2** requires a session token and is recommended for improved security.

### 48. EC2 Reserved Instances (Regional)
**Regional RIs** apply automatically to matching instance usage in any AZ within the region. They provide **cost savings** but **do not reserve capacity**, so they won’t guarantee launch success during peak times.

### 49. EC2 Reserved Instances (Zonal)
**Zonal RIs** are tied to a specific AZ and provide both **cost savings** and a **capacity reservation**. Useful when you need guaranteed availability in a particular zone.

### 50. ElastiCache: Redis vs Memcached
- **Redis**: Supports persistence, replication, pub/sub, and complex data types. Better for durability and structured caching.
- **Memcached**: Simpler, in-memory key-value store. Better for high-speed, read-heavy, stateless caching use cases.

### 51. Elastic Beanstalk Instance Recovery
If an instance in an Elastic Beanstalk environment fails a health check, Beanstalk automatically **replaces it** and deploys the **last successfully deployed application version** to the new instance.

### 52. Elastic Beanstalk Serverless?
Elastic Beanstalk is **not serverless**—it manages **EC2 instances, ASGs, and load balancers** for you. While it automates infrastructure management, the underlying resources are still provisioned and billed individually.

### 53. Ephemeral Ports in EC2/ELB Communication
When an EC2 instance responds to an incoming request (e.g., from an ELB), it uses **ephemeral ports** in the range **1024–65535**. These must be allowed in **security groups** and **NACLs** for proper communication.

### 54. EventBridge (CloudWatch Events) Rules
AWS EventBridge (formerly CloudWatch Events) allows you to define **event rules** to trigger actions like **Lambda functions**, **Step Functions**, or **ECS tasks**. You can trigger on AWS service events or use **cron expressions** for scheduled events.

### 55. Export DynamoDB with Data Pipeline
AWS Data Pipeline can be used to **export DynamoDB data to S3**, optionally on a schedule. It supports **cross-account S3 destinations**, but this method is considered legacy in favor of newer tools like Glue or native export.

### 56. Export DynamoDB with EMR (Hive)
Using **Hive on Amazon EMR**, you can create **external tables** that point to DynamoDB and then export data to **S3** using Hive queries. This method is powerful for large-scale analytics but requires setup of EMR clusters.

### 57. Export DynamoDB with Glue
AWS Glue can extract data from **DynamoDB**, transform it (ETL), and load it into **Amazon S3** in a structured format (e.g., Parquet or CSV). The resulting files are **downloadable** and can be used in analytics pipelines.

### 58. Gateway VPC Endpoint for DynamoDB
A **Gateway VPC endpoint** allows your VPC to **privately access DynamoDB** without traversing the internet or requiring a NAT gateway. This enhances **security** and **reduces data transfer costs**.

### 59. How Elastic Beanstalk operates EC2 instances
Elastic Beanstalk uses an **Auto Scaling Group (ASG)** and an **Application Load Balancer (ALB)** under the hood to deploy and manage EC2 instances. It performs **health checks**, handles **rolling deployments**, and maintains **version history**.

### 60. IAM Access Analyzer
IAM Access Analyzer inspects your AWS environment for **resource-based policies** that allow **public** or **cross-account access**. It helps identify potential security risks and is especially useful for monitoring **S3, KMS, IAM roles**, and **SNS**.

### 61. IAM Authorization with SigV4 & API GW
When using **AWS_IAM** as the authorization type in API Gateway, clients must send **SigV4-signed requests**. This method is best for **service-to-service APIs**, but not ideal for public-facing APIs due to credential complexity.

### 62. IAM credential types for CodeCommit
To access **AWS CodeCommit**, IAM users can use:
- **SSH keys** (configure in IAM user settings)
- **Git credentials** (username/password managed in IAM)
- **AWS access keys** (for automation or CLI usage)

### 63. Immediate forecast if usage exists
If an AWS Budget has access to **at least 5 weeks of past usage data**, it can generate a **forecast immediately** upon creation. Otherwise, it may take time to accumulate sufficient data.

### 64. Invalidate API Gateway Cache
To **bypass or refresh API Gateway’s cache**, send the following header: `Cache-Control: max-age=0`
This forces the request to go to the backend instead of returning the cached response.

### 65. KMS direct encryption behavior
KMS can **directly encrypt up to 4 KB** of data. For larger payloads, AWS uses **envelope encryption**, where KMS encrypts a data key, and that key encrypts your actual data client-side.

### 66. KMS encryption process
KMS manages **Customer Master Keys (CMKs)** in a secure fashion and performs **cryptographic operations** within its own infrastructure. Client applications send data or keys to encrypt, and KMS returns the encrypted result.

### 67. Lambda Authorizer vs Cognito User Pools
- **Lambda Authorizer**: Use custom logic to allow/deny access based on headers, tokens, IPs, etc.
- **Cognito User Pools**: Provides managed user directories, authentication flows, and token-based access.

Choose based on whether you need **custom auth** or **managed user identity**.

### 68. Lambda Package Size Limits
Lambda limits:
- **50 MB zipped** package (when uploaded via CLI or console)
- **250 MB unzipped** (when uploaded via S3)
- **5 layers** max per function, **each up to 50 MB zipped**

Package size affects cold start times and deployment strategy.

### 69. MOCK Integrations in API Gateway
**MOCK integration** allows API Gateway to return a **hardcoded response** without invoking a backend service. Useful for prototyping, testing, or returning static content like maintenance messages.

### 70. Origin Group in CloudFront
An **Origin Group** in CloudFront lets you define a **primary and secondary origin**. If the primary origin fails (e.g., 5xx errors or timeout), CloudFront automatically fails over to the secondary origin.

### 71. Public APIs with API Keys
API Gateway supports **API Keys** to identify clients like web and mobile apps. API Keys enable **usage plans** to throttle or meter usage. Use in combination with **Lambda Authorizers** to validate the key’s authenticity and permissions.

### 72. RCU and WCU in DynamoDB
- **RCU (Read Capacity Unit)**: 1 RCU = 1 strongly consistent read per second (or 2 eventually consistent reads) of up to 4 KB.
- **WCU (Write Capacity Unit)**: 1 WCU = 1 write per second for items up to 1 KB.
Choose provisioned or on-demand mode based on traffic patterns.

### 73. Redis Cluster and Cluster Mode
In **Redis Cluster Mode**, data is **sharded across multiple nodes**, improving scalability and availability. It requires a **cluster-aware client** to route operations to the correct shard. Enables automatic failover and partitioning.

### 74. S3 CLI: Pagination Options
When listing large datasets in S3 via CLI, use:
- `--max-items`: Limit the total items returned.
- `--page-size`: Set number of items per API call.
- `--starting-token`: Resume from a previous point.
These options improve efficiency in scripting and automation.

### 75. S3 Event Notifications to SNS
Amazon S3 can **send notifications to SNS** when specific events occur (e.g., object creation). This can trigger downstream services, alerting mechanisms, or workflows. Configuration is per-bucket and can filter by prefix/suffix.

### 76. S3 Replication (SRR/CRR)
- **SRR (Same-Region Replication)**: Replicates objects between buckets in the same region.
- **CRR (Cross-Region Replication)**: Replicates across AWS regions.
Useful for backup, compliance, and latency reduction. Requires versioning enabled on both source and destination.

### 77. S3 Select
S3 Select lets you **query specific rows/columns** from S3 objects (CSV, JSON, Parquet) using **SQL-like syntax**. It minimizes data transfer and speeds up processing by returning only required data instead of entire files.

### 78. S3 Versioning & Null Version
When you enable **versioning** on an S3 bucket:
- Pre-existing objects are assigned a **null version ID**.
- New objects get **unique version IDs**.
- Deleting creates a **delete marker**, which hides the object unless version ID is specified.

### 79. SNS Filter Policy
An SNS **filter policy** lets you selectively deliver messages to subscribers based on **message attributes**. Subscribers only receive messages that match the policy, reducing noise and improving targeting.

### 80. SNS Subscription
An **SNS subscription** defines:
- The **protocol** (e.g., HTTP, Lambda, email)
- The **endpoint** (e.g., URL or Lambda ARN)
It represents how and where messages from an SNS topic will be delivered.

### 81. SNS Topic
An **SNS topic** is a pub/sub communication channel that allows **one-to-many messaging**. Publishers send messages to the topic, which are then **fan-out** to all subscribed endpoints (e.g., Lambda, SQS, email, HTTPS).

### 82. SQS Dead-Letter Queues (DLQ)
A **DLQ** stores messages that **fail to process successfully** after a configured number of attempts. Useful for debugging and isolating problematic messages without blocking the main queue.

### 83. SQS Extended Client
The **SQS Extended Client** (Java library) allows sending **large payloads** by storing them in **S3** and sending a reference in the SQS message. It helps avoid hitting the 256 KB message size limit.

### 84. SQS FIFO Options
FIFO queues require:
- `MessageGroupId` (mandatory): Preserves order per group.
- `MessageDeduplicationId` or `ContentBasedDeduplication`: Prevents duplicates.
Ensures **strict ordering** and **exactly-once delivery** within a group.

### 85. SQS: MessageGroupId in Standard Queue
The `MessageGroupId` field is only supported in **FIFO queues**. Attempting to use it in a **standard queue** will result in a validation error. Standard queues do not guarantee order or deduplication.

### 86. SSE-C and S3 + HTTP Restriction
When using **SSE-C (Server-Side Encryption with Customer-Provided Keys)**, all requests to S3 must use **HTTPS**. AWS enforces encryption in transit to protect the customer-provided key.

### 87. SSE-S3 Costs and Limitations
**SSE-S3** uses S3-managed keys for encryption. It’s **free**, **low-latency**, and provides strong encryption, but it:
- Can’t be reused outside of S3.
- Doesn’t offer audit control like SSE-KMS.

### 88. SSM SecureString for Secrets
**AWS Systems Manager Parameter Store** allows you to store sensitive data as **SecureString** parameters. These are encrypted using **KMS** and can be referenced by EC2, Lambda, or ECS apps.

### 89. STS Service Responsibilities
**AWS STS** provides:
- **Temporary credentials** via AssumeRole or federation.
- Role assumption for cross-account access.
- **Error decoding** for tokens or policy mismatches.

Used for federated access, delegation, and limited-session permissions.

### 90. Send Data to Kinesis from EC2
You can stream data to Kinesis using:
- **AWS SDK / CLI** for custom apps
- **Kinesis Agent** to monitor files/logs
- **Kinesis Producer Library (KPL)** for high-performance batching
Choose based on language, source type, and throughput needs.

### 91. Shared Volume (EFS)
**Amazon EFS** allows multiple EC2 instances to mount the same file system **concurrently**, even across **Availability Zones**. It supports NFS protocol and is useful for shared storage needs, such as CMS, media apps, and data science.

### 92. Stack vs Subnet Concepts in CloudFormation
In CloudFormation, a **stack** is a collection of AWS resources managed as a unit. A **subnet** is typically declared within the stack using a resource of type `AWS::EC2::Subnet`. Understanding subnet placement is crucial when templating VPC-based architectures.

### 93. Standard CloudWatch EC2 Metrics
Standard (basic) monitoring in EC2 includes metrics like:
- **CPUUtilization**
- **NetworkIn / NetworkOut**
- **DiskReadOps / DiskWriteOps**
It **does not include memory usage** unless you install the CloudWatch agent.

### 94. Step Functions Workflow Types
- **Standard Workflows**: Durable and support long-running processes (up to 1 year).
- **Express Workflows**: High-performance, cost-efficient for short-lived or high-volume workflows (up to 5 minutes).

### 95. Subnet Logs
There are no direct "subnet logs" in AWS. However, you can **enable VPC Flow Logs** at the **subnet level** to monitor traffic going in and out, including metadata like source/destination IPs and ports.

### 96. Triggering Beanstalk Workers
Elastic Beanstalk Worker environments are designed to **only respond to SQS messages**. They cannot be triggered by HTTP requests, EventBridge, or other event sources directly.

### 97. VPC Flow Logs
**VPC Flow Logs** capture metadata about IP traffic going to and from network interfaces in your VPC. You can log at the **VPC**, **Subnet**, or **ENI** level and export logs to **CloudWatch** or **S3**.

### 98. VPN Logs
VPN logs help monitor:
- **Tunnel status** and uptime
- **Client connections** for Client VPN endpoints
Logs are available via **CloudWatch Logs**, if configured in the VPN connection or Client VPN setup.

### 99. X-Ray Annotations & Indexes
In AWS X-Ray:
- **Annotations** are indexed and used to **filter/group traces** in the console. They support `string`, `number`, and `boolean` types.
- **Metadata** is not indexed and is only visible in the full trace details for debugging purposes.

### 100. X-Ray Sampling Feature
**Sampling** lets X-Ray trace only a subset of requests. This reduces **cost** and **data volume** while still providing representative performance insights. You can configure fixed-rate sampling rules or use dynamic rules based on request attributes.

### 101. CloudFront: Cognito Integration Limitation
**CloudFront does not natively integrate with Amazon Cognito** for authentication. You must implement custom authentication flows using Lambda@Edge, signed URLs/cookies, or use Cognito with API Gateway or ALB instead.

### 102. CloudFront: Origin Group Failover
**Origin Groups** in CloudFront allow only **one primary** and **one secondary origin**. If the primary fails (based on HTTP codes or timeouts), it falls back to the secondary. It is **not** a load-balancing solution.

### 103. CodeDeploy: Deployment Configurations
CodeDeploy offers built-in configurations to control rollout pace:
- `CodeDeployDefault.AllAtOnce`
- `CodeDeployDefault.HalfAtATime`
- `CodeDeployDefault.OneAtATime`
You can also define **custom configurations** to control batch sizes and wait durations.

### 104. CodeDeploy: Deployment Group
A **Deployment Group** specifies:
- **Deployment targets** (EC2, Lambda, ECS)
- **Deployment config** (AllAtOnce, etc.)
- **Auto-scaling groups**, **tags**, and **load balancer settings**
It determines **where and how** your application is deployed.

### 105. CodeDeploy: Rollback and Hooks
CodeDeploy supports:
- **Lifecycle event hooks** (e.g., BeforeInstall, AfterInstall)
- **Rollbacks** triggered by failed hooks or **CloudWatch alarms**
- Integration with **load balancers** to remove unhealthy instances

### 106. DynamoDB: Conflict Handling in Global Tables
In **DynamoDB Global Tables**, replication is **eventually consistent** and **asynchronous**. If the same item is updated in two regions simultaneously, **last writer wins** based on timestamps.

### 107. DynamoDB: Global Tables for Global Users
**Global Tables** replicate DynamoDB tables across regions automatically. They reduce **latency** for globally distributed users and improve **availability** and **disaster recovery**.

### 108. EBS: CreateVolume Not in CloudTrail (EC2 launch)
When you launch an EC2 instance, the **EBS volume is created implicitly**, but this `CreateVolume` action is **not logged** in CloudTrail. Only explicit calls to `CreateVolume` are tracked.

### 109. EBS: Region-Wide Encryption by Default
If **encryption-by-default** is enabled for EBS in a region, **all new volumes are encrypted** automatically. This **cannot be overridden** at the individual volume level unless the region-wide setting is changed.

### 110. EC2: Multi-AZ RDS
When using **RDS in Multi-AZ mode**, AWS provisions a **standby instance in a separate AZ**. On failure of the primary instance, failover is automatic, ensuring **high availability** and **minimal downtime**.

### 111. ECR: `get-login --no-include-email`
The old command `aws ecr get-login --no-include-email` was used to authenticate Docker with Amazon ECR. It is now deprecated in favor of:
```bash
aws ecr get-login-password | docker login --username AWS --password-stdin <aws_account_id>.dkr.ecr.<region>.amazonaws.com
```

### 112. IAM Policy: "Resource": "*" Meaning
The `"Resource": "*"` element in an IAM policy grants access to **all resources** for the specified action(s). It’s often used when the resource can’t be narrowed down (e.g., `logs:CreateLogGroup`) or when permission must be broad across services.

### 113. RDS vs Read Replicas
- **Multi-AZ** RDS instances are designed for **high availability** (HA) and automatic failover.
- **Read Replicas** are used to **scale read traffic** and improve performance but are not suitable for HA since replication is asynchronous.

### 114. S3: CloudFront Signed URLs/Cookies
CloudFront can restrict access to private S3 content using **signed URLs** or **signed cookies**, which are time-limited and enforce download permissions. This method is **independent of Cognito** and uses key pairs owned by the AWS root user.

### 115. S3: Encryption by Default
S3 allows you to enable **encryption by default** on a bucket or region level. Once enabled, **all new objects are encrypted** using the selected method (SSE-S3, SSE-KMS). You cannot selectively disable encryption per object.

### 116. S3: Eventual Consistency on Bucket Deletion
S3 uses **eventual consistency** for bucket listings. After deleting a bucket, it may still appear in `ListBuckets` responses for a short period until the deletion propagates fully across the system.

### 117. S3: Simultaneous Writes & Event Notifications
In **non-versioned S3 buckets**, if two clients write to the same object at the same time, **only one event notification** might be triggered. This happens due to **write coalescing** and eventual consistency.

### 118. SQS: Max Number of Messages
In Amazon SQS, a single `ReceiveMessage` API call can retrieve up to **10 messages** using the `MaxNumberOfMessages` parameter. Fewer messages may be returned if fewer are available or if visibility timeouts are in effect.

### 119. STS: Role Assumption by API Gateway
API Gateway can assume an IAM role using **AWS STS** to perform actions like writing logs to CloudWatch. This is configured by assigning a **trust policy** that allows API Gateway to assume the role securely.

### 120. STS: Why It’s Needed
**AWS Security Token Service (STS)** is required when temporary credentials are needed:
- To allow **limited, time-bound access**
- For **role assumption** across accounts/services
- For **secure service integration** (like API Gateway writing logs without embedding long-term credentials)

### 121. `appspec.yml` vs `buildspec.yml`
- **`appspec.yml`**: Used by **CodeDeploy** to define deployment hooks and scripts (e.g., `BeforeInstall`, `AfterInstall`) during an application rollout.
- **`buildspec.yml`**: Used by **CodeBuild** to define build instructions (e.g., install, build, test, post-build phases) in a YAML format.

### 122. `cdk deploy`
The `cdk deploy` command:
- **Synthesizes** your CDK app into a CloudFormation template
- **Deploys** it to AWS using CloudFormation
It’s the primary command for launching or updating stacks managed via the AWS CDK.

### 123. `cdk diff`
The `cdk diff` command compares your **current CDK app code** with the **deployed stack** and outputs the **differences**, showing what will be created, updated, or deleted. Useful for reviewing changes before running `cdk deploy`.

### 124. `sam deploy`
Used to deploy AWS SAM applications. It packages and deploys the code and infrastructure using **CloudFormation**, similar to `cdk deploy`. It creates or updates full stacks.

### 125. `sam sync`
A fast, iterative tool for **updating existing resources** in a SAM application (e.g., Lambda code, environment variables). It **does not create new resources** and is ideal for development/test cycles.

### 126. ecs.config File
The `ecs.config` file on an **EC2 instance running ECS agent** allows configuration of the agent’s behavior. Examples:
- Specify the ECS cluster name
- Set logging options
- Define container instance attributes
The file is typically placed at `/etc/ecs/ecs.config`.
