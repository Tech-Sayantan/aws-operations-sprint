# TICKET-001 Access Request

## Summary
Grant a developer temporary read-only access to the `dev` environment.

## Type
Access

## Requester
Application developer

## Environment
dev

## Business Reason
Investigate logs and validate a feature deployment.

## Resources Affected
IAM Identity Center permission set, IAM role, CloudWatch read permissions

## Risk Level
low

## Approval
pending

## Rollback Plan
Remove the permission set assignment and revoke the role mapping.

## Implementation Notes
Use least privilege and add an expiry date.

## Verification
Confirm access works only for the requested read-only actions.

## Evidence
Add IAM/SSO assignment details and verification notes.

