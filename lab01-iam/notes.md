## Goal
Demonstrate basic identity and access control in AWS using IAM and least-privilege principles.

## Status
Completed.

## Access Model
Root account  
→ IAM Group (`S3ReadOnlyGroup`)  
→ IAM User (`dev-user`)  
→ AWS Services (S3 allowed, EC2 denied)

## Configuration
- IAM group with `AmazonS3ReadOnlyAccess` policy  
  - [IAM group and attached policy](screenshots/iam-group-policy.png)
- IAM user with console access
- Permissions assigned via group only
- No direct user policies
- No administrative or billing permissions granted

## What I did
- Logged in with the root account for initial setup only
- Created an IAM group with read-only S3 permissions
- Created an IAM user and added it to the group
- Logged in as the IAM user using the account-specific login URL
- Verified denied access to EC2 and account/billing information  
  - [EC2 access denied due to missing permissions](screenshots/ec2-access-denied.png)

