# AureumDesk Security

## Required controls
- HTTPS
- Input validation
- Authentication and RBAC
- Organization-level data isolation
- Webhook signature verification
- Rate limiting
- Secrets Manager/environment secrets
- Least-privilege IAM
- Audit events
- Correlation IDs
- Safe errors
- Protected logs
- Secret scanning where practical

## Healthcare development
Use synthetic patient data only. Do not place real patient records, conversations, credentials or audio in development or source control.

## AI boundary
The healthcare assistant is administrative/support software and must not autonomously diagnose, prescribe, change medication, authorize dispensing or make clinical decisions.