# AWS Certified Developer – Associate: Mock exam 1 notes

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

