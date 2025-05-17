# AWS Certified Developer – Associate Exam Notes

This repository contains categorized and logically ordered notes to help you prepare for the **AWS Certified Developer – Associate** exam. Topics are arranged from basic foundational services (like S3 and CloudFront) to more advanced orchestration, ETL, and infrastructure concepts.

---

## Cheat Sheet Table (Ordered from Basic to Advanced)

| #  | Topic                                  | Cheat Sheet Summary                                                |
|----|----------------------------------------|--------------------------------------------------------------------|
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
