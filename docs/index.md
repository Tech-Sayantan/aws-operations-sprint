---
title: AWS Operations Sprint
---

# AWS Operations Sprint

This site is the documentation front door for the AWS Operations Sprint lab.

## What This Lab Practices

This lab models real CloudOps work:

- a request arrives as a ticket
- the request is reviewed and approved
- the change is implemented through Git and infrastructure as code
- validation evidence is attached
- the ticket is closed with a rollback note

## Start Here

1. Read [GitHub Platform Components](github-platform-components.md)
2. Read [CloudOps Ticket Lifecycle](CLOUDOPS-TICKET-LIFECYCLE.md)
3. Follow [Day 1: CloudOps Ticket Flow](https://github.com/Tech-Sayantan/aws-operations-sprint/blob/main/syllabus/DAY-1.md)
4. Open the [GitHub Project board](https://github.com/users/Tech-Sayantan/projects/1)
5. Pick [TICKET-001](https://github.com/Tech-Sayantan/aws-operations-sprint/issues/1)

## Repository Areas

- `tickets/` stores local ticket examples and templates
- `.github/ISSUE_TEMPLATE/` defines GitHub Issue forms
- `.github/pull_request_template.md` defines PR review questions
- `terraform/` will hold AWS infrastructure code
- `ansible/` will hold server operations automation
- `evidence/` will hold verification notes
- `docs/` powers this documentation site

## Current Sprint

The first week focuses on AWS operations fundamentals:

- Day 1: ticket flow, approvals, evidence
- Day 2: IAM and access
- Day 3: S3 and KMS
- Day 4: VPC, Security Groups, NACLs
- Day 5: EC2, EBS, Ansible or SSM
- Day 6: CloudWatch, CloudTrail, AWS Config
- Day 7: final demo and interview story
