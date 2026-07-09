---
title: GitHub Platform Components
---

# GitHub Platform Components

GitHub can behave like a lightweight engineering platform, similar in spirit to Azure DevOps.

It is not exactly the same product, but the building blocks map very well.

## The Main Components

| Need | GitHub Component | Real-World Use Case |
| --- | --- | --- |
| Source code | Repository | Store Terraform, Ansible, app code, docs, runbooks |
| Ticketing | Issues | Track requests like access, S3 bucket, SG rule, disk resize |
| Planning board | Projects | Move work through New, Triage, Approved, In Progress, Done |
| Code review | Pull Requests | Review Terraform or Ansible changes before they run |
| Pipelines | GitHub Actions | Run tests, Terraform plan, security scan, deployment |
| Documentation site | GitHub Pages | Publish lab notes, runbooks, architecture, demo guide |
| Security controls | Branch protection and CODEOWNERS | Require review before production changes |
| Reusable automation | Actions and workflows | Repeat the same validation for every lab |
| Release history | Tags and Releases | Mark stable lab milestones or demo versions |

## Repository

A repository is the source of truth.

For this lab, the repo stores:

- tickets
- documentation
- Terraform layout
- Ansible layout
- evidence files
- GitHub templates

Real scenario:

An operations team keeps all infrastructure changes in a repository so every change has history, review, and rollback.

## Issues

Issues are tickets.

Examples:

- "Grant read-only access to dev"
- "Create encrypted S3 bucket"
- "Allow app server to reach database on 5432"
- "Resize EBS volume from 50 GB to 100 GB"

Real scenario:

An app team raises an issue. CloudOps checks business reason, risk, approval, and rollback before implementation.

## Projects

Projects are project management boards.

They are useful for:

- seeing all open work
- grouping tickets by status
- tracking what is approved
- showing what is blocked
- planning a sprint

Real scenario:

A CloudOps manager opens the Project board in the morning and sees which requests are new, approved, waiting for evidence, or done.

## Pull Requests

Pull Requests are reviewed changes.

In CloudOps, a PR can include:

- Terraform code
- Ansible playbooks
- ticket updates
- evidence notes
- documentation updates

Real scenario:

A network request asks for port 5432. The PR changes only the specific Security Group rule, shows the Terraform plan, and documents rollback.

## GitHub Actions

GitHub Actions are pipelines.

They can run:

- Terraform format check
- Terraform validate
- Terraform plan
- Checkov or tfsec security scan
- Ansible lint
- documentation build
- deployment after approval

Real scenario:

When a PR changes Terraform, GitHub Actions automatically runs `terraform plan` and posts whether the change is safe to review.

## GitHub Pages

GitHub Pages publishes documentation as a website.

It is useful when a lab needs:

- a readable homepage
- architecture notes
- step-by-step guides
- runbooks
- interview talking points
- demo instructions

Real scenario:

Instead of sending someone into a repo full of folders, you share one Pages URL that explains the lab and links to the right files.

## Branch Protection

Branch protection controls how changes enter `main`.

It can require:

- pull request review
- passing pipeline checks
- no direct push
- signed commits

Real scenario:

Production Terraform cannot be merged until another engineer reviews it and the plan pipeline passes.

## CODEOWNERS

CODEOWNERS assigns reviewers automatically.

Examples:

- security team reviews IAM changes
- network team reviews Security Group changes
- platform team reviews Terraform modules

Real scenario:

If a PR touches `terraform/modules/iam`, GitHub automatically requests review from the access-control owner.

## GitHub vs Azure DevOps

| Azure DevOps | GitHub Equivalent |
| --- | --- |
| Azure Repos | GitHub Repositories |
| Azure Boards | GitHub Issues and Projects |
| Azure Pipelines | GitHub Actions |
| Azure Wiki | GitHub Pages or repo docs |
| Pull Requests | Pull Requests |
| Service Connections | GitHub OIDC and repository secrets |
| Environments | GitHub Environments |

## For Our Labs

Use this pattern for most labs:

- repo for code
- issues for tasks
- project for tracking
- actions for validation
- pages for documentation

This gives the lab a professional shape and makes it easier to explain in interviews.

