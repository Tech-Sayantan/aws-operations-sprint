# TICKET-003 Security Group Request

## Summary
Allow the app server to reach the database on port 5432.

## Type
Network

## Requester
Backend team

## Environment
dev

## Business Reason
Application cannot connect to the database after deployment.

## Resources Affected
Security group inbound rule, possibly NACL review

## Risk Level
medium

## Approval
pending

## Rollback Plan
Remove the inbound rule and confirm traffic is blocked again.

## Implementation Notes
Prefer Security Group changes before touching NACLs.

## Verification
Test connectivity from the app host only.

## Evidence
Add before/after rule snapshots and test result.

