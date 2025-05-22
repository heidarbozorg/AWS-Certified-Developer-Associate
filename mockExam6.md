# AWS Certified Developer – Associate: Mock exam 6 notes

## Cheat Sheet Table

| #  | Topic                                                | Summary                                                                 |
|----|------------------------------------------------------|-------------------------------------------------------------------------|
| 1  | S3: Eventual Consistency on Bucket Deletion          | Deleted bucket might still appear due to eventual consistency.         |
| 2  | S3: Simultaneous Writes & Event Notifications        | Simultaneous writes to non-versioned object may trigger only one event.|
| 3  | S3: Encryption by Default                            | Region-wide setting; can't disable encryption for individual resources.|
| 4  | S3: CloudFront Signed URLs/Cookies                   | Used to restrict access to S3 via CloudFront; not related to Cognito.  |

| 5  | CloudFront: Cognito Integration Limitation           | CloudFront does not natively support Cognito authentication.           |
| 6  | CloudFront: Origin Group Failover                    | Only one primary and one secondary origin per group; not load-balanced.|

| 7  | EBS: CreateVolume Not in CloudTrail (EC2 launch)     | EBS volumes created during EC2 launch won’t log `CreateVolume` in CT.  |
| 8  | EBS: Region-Wide Encryption by Default               | Cannot turn off encryption per volume once default is enabled.         |

| 9  | EC2: Multi-AZ RDS                                    | Provides automatic failover and high availability via standby instance.|
| 10 | RDS vs Read Replicas                                 | Multi-AZ is for HA, Read Replicas are for scalability (read traffic).  |

| 11 | STS: Role Assumption by API Gateway                  | API Gateway uses STS to assume an IAM role for CloudWatch logging.     |
| 12 | STS: Why It’s Needed                                 | Used to get temporary credentials to write logs securely.              |
| 13 | IAM Policy: `"Resource": "*"` Meaning                | Grants permissions for all resources; used when targets are dynamic.   |

| 14 | SQS: Max Number of Messages                          | You can retrieve up to 10 messages in a single `ReceiveMessage` call.  |

| 15 | CodeDeploy: Deployment Group                         | Defines where and how deployments occur; can target EC2, Lambda, or ECS.|
| 16 | CodeDeploy: Deployment Configurations                | Controls deployment speed (AllAtOnce, HalfAtATime, OneAtATime).        |
| 17 | CodeDeploy: Rollback and Hooks                       | Supports lifecycle events, alarm-based rollbacks, and load balancer integration.|

| 18 | ECR: `get-login --no-include-email`                  | Authenticates Docker to ECR; now deprecated in favor of `get-login-password`.|

| 19 | DynamoDB: Global Tables for Global Users             | Use Global Tables to reduce latency for globally distributed users.     |
| 20 | DynamoDB: Conflict Handling in Global Tables         | Last writer wins (based on timestamp); replication is asynchronous.     |
