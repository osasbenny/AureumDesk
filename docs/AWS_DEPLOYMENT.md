# AureumDesk AWS Deployment

## Target
Small, secure, production-minded AWS footprint.

## Candidate services
- RDS PostgreSQL
- ECS/Fargate or App Runner
- SQS
- EventBridge where useful
- S3
- Secrets Manager
- CloudWatch
- IAM
- API Gateway or load balancer
- WAF where appropriate

## Environments
local, development/test, production.

## Requirements
Use least privilege. Keep secrets in environment/Secrets Manager. Do not commit credentials. Add health/readiness checks, logs and rollback guidance.

If production AWS credentials are unavailable, create infrastructure definitions and exact deployment instructions without claiming that deployment occurred.