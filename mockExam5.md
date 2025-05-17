# AWS Certified Developer – Associate: Mock exam 5 notes

## Cheat Sheet Table

| #  | Topic                                     | Cheat Sheet Summary |
|----|-------------------------------------------|----------------------|
| 1  | X-Ray Annotations & Indexes              | Use **Annotations** (simple key-value pairs) for **filtering** and **grouping traces** in X-Ray; searchable types: `string`, `number`, `boolean`. Metadata is **not indexed** and used for debugging only. |
| 2  | EC2 Instance Metadata                     | Query instance metadata at `http://169.254.169.254/latest/meta-data/` to get instance ID, IP, security groups, etc. Use **IMDSv2** (token-based) for improved security. |
| 3  | S3 Versioning & Null Version             | Objects uploaded before versioning have a `null` version ID. Uploads after enabling versioning get unique IDs. After a delete, a **delete marker** is created with its own version ID. |
| 4  | SQS FIFO Options                          | Use `MessageGroupId` (required), `MessageDeduplicationId`, or `ContentBasedDeduplication` to ensure **strict ordering** and **exactly-once processing** in FIFO queues. |
| 5  | SQS: MessageGroupId in Standard Queue     | `MessageGroupId` is **only supported in FIFO queues**. Standard queues do not guarantee order or support this field. Attempting to use it causes a validation error. |
| 6  | AWS CodeStar                              | AWS CodeStar provides an all-in-one UI to create, manage, and deploy applications using CodeCommit, CodeBuild, CodePipeline, and CodeDeploy. Great for small teams and rapid setup. |
| 7  | Amazon Macie                              | A security service that uses ML to scan S3 for **PII** and sensitive data. Outputs **findings**, not enforcement. Good for **compliance** and **data classification**. |
| 8  | Beanstalk Docker & Custom Platforms       | Choose from Single-container Docker, Multi-container (via ECS), or Custom Platforms (via Packer). `Dockerrun.aws.json v1` for single; `v2` for multi-container. |
| 9  | S3 Select                                 | Allows querying a **subset of data** from S3 objects using **SQL-like expressions**. Reduces data transfer and processing costs. Supports CSV, JSON, and Parquet. |
| 10 | IAM Authorization with SigV4 & API GW     | Use **SigV4-signed requests** for **IAM-based auth** in API Gateway (`AWS_IAM`). Great for service-to-service. Not suitable for public apps. |
| 11 | Public APIs with API Keys                 | Use **API Keys** in API Gateway to **identify and throttle** access from known clients (web, mobile). Combine with Lambda authorizer for better validation. |
| 12 | Beanstalk Worker & `cron.yaml`            | In a Worker environment, use `cron.yaml` to define scheduled jobs. Beanstalk will POST to defined routes based on cron expressions (in UTC). |
| 13 | S3 CLI: Pagination Options                | Use `--max-items` (limit total returned), `--page-size` (items per API call), `--starting-token` (resume pagination). All useful for **efficient batch processing**. |
| 14 | AWS KMS: Data Key Caching                 | Use the **AWS Encryption SDK** with **data key caching** to reduce KMS API costs. Caches data keys in memory for reuse with TTL and usage limits. |
| 15 | Beanstalk: Rolling with Additional Batch  | Deployment strategy that **adds a temporary batch of instances** during updates, ensuring **no downtime**. Great for production apps needing high availability. |

---
