# AWS Certified Developer – Associate: Mock exam 4 notes

---

## Cheat Sheet Table

| #  | Topic                                      | Cheat Sheet Summary                                                    |
| -- | ------------------------------------------ | ---------------------------------------------------------------------- |
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

---
