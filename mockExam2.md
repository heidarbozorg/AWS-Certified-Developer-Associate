# AWS Certified Developer – Associate: Mock exam 2 notes

## Cheat Sheet Table

| #  | Topic                                      | Summary                                                                 |
|----|--------------------------------------------|-------------------------------------------------------------------------|
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

