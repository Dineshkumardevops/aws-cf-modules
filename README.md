1. Deployment of API Authentication to ECS
Discussion Points:
Issue: API Authentication service deployment is blocked due to a missing database connection.
Observation:
The service starts but continuously retries and reprovisions.
The Docker Compose setup references a database connection that is not available.
Conclusion: Deployment is blocked until RDS is set up.
Next Steps:
[Speaker 1] to complete RDS setup to resolve the database connection issue.
2. Infrastructure Management: CloudFormation vs. CDK vs. Terraform
Discussion Points:
CDK:
Already on the approved list and is expected to simplify management.
AWS recommends using CDK.
CloudFormation:
Potential scalability and manageability issues due to multiple environments and containers.
Concerns over excessive copy-pasting and maintenance effort.
Terraform:
Offers multi-cloud flexibility, but introduces additional learning overhead for the team.
Not a priority unless CloudFormation/CDK becomes unmanageable.
Conclusion:
Continue using CloudFormation unless it proves to be too complex.
Decision on whether to switch to CDK to be made by March 31, 2025.
Next Steps:
[Speaker 3] to evaluate CloudFormation feasibility and decide on CDK adoption.
3. RDS and MQ Setup
Discussion Points:
RDS Setup:
Required for API Authentication deployment.
Will follow an existing provisioning script to avoid redundancy.
MQ Setup:
Not needed for API Authentication, but required for other services.
Will be set up after RDS is completed.
Conclusion:
RDS setup is the immediate priority for enabling API Authentication.
MQ setup will follow.
Next Steps:
[Speaker 1] to complete RDS setup, then move to MQ setup.
4. Open Items / Pending Decisions
Final decision on CloudFormation vs. CDK pending. Deadline: March 31, 2025.
RDS setup must be completed to resolve the database connection issue. Details require further clarification.
5. Next Meeting
Date: March 15, 2025
Agenda:

RDS deployment review
API authentication validation
CloudFormation vs. CDK decision progress

Backup & Restore Process:
Backups will not be automated; instead, they will be manually uploaded to S3.
Restore steps must be clearly defined, as a manual restore might be required.
IAM roles and permissions for backup and restore must be reviewed.
Database connection strings need to be correctly configured in the environment.
Alternative: A manual database setup is possible for development/testing.
