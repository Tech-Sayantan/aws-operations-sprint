# CloudOps Ticket Lifecycle

## Why Tickets Matter

In real AWS operations, most work begins with a request from an application team, developer, security team, or manager.

Examples:

- grant read-only access
- create an encrypted S3 bucket
- open a database port from one app to another
- resize an EBS volume
- install a package on a server
- create a CloudWatch alarm

The ticket protects the team from unclear, risky, or unaudited work.

## Lifecycle

```text
new -> triage -> approved -> in progress -> verification -> done
```

## New

The request arrives.

CloudOps checks:

- is the requester clear?
- is the environment clear?
- is the business reason clear?
- are the affected resources clear?

## Triage

CloudOps classifies the request.

Common categories:

- access
- storage
- network
- compute
- monitoring
- audit
- patching

## Approved

Someone with authority accepts the risk.

For low-risk dev changes, approval may be lightweight.
For production access or network changes, approval should be stricter.

## In Progress

Implementation begins.

Typical implementation tools:

- Terraform for AWS infrastructure
- Ansible or AWS Systems Manager for server configuration
- GitHub Actions for validation and controlled execution

## Verification

CloudOps proves the change works.

Examples:

- IAM role can only read, not write
- bucket has encryption and public access block
- app host can reach DB port, but the internet cannot
- disk size increased and filesystem sees the new size

## Done

The ticket is closed only after evidence is attached.

Evidence examples:

- Terraform plan summary
- command output
- AWS console screenshot
- CloudTrail event
- rollback note

## Terraform vs Ansible

Use Terraform when the desired state is an AWS resource:

- IAM role
- S3 bucket
- security group rule
- EC2 instance
- EBS volume
- CloudWatch alarm

Use Ansible or SSM when the desired state is inside a server:

- install package
- update config
- restart service
- patch OS
- grow filesystem after disk expansion

