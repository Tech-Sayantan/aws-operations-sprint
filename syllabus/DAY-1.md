# Day 1: CloudOps Ticket Flow

Day 1 is about learning the shape of real AWS operations work before touching paid AWS resources.

## Mental Model

A CloudOps team usually does not change AWS resources randomly from the console.
Most changes start as a ticket, become a reviewed pull request, get validated, then end with evidence.

Basic flow:

```text
request -> triage -> approval -> implementation -> validation -> evidence -> close
```

## Key Concepts

### Ticket

A ticket is the business request.

It answers:

- who is asking?
- what environment is affected?
- why is the change needed?
- what is the risk?
- how do we roll back?

### Pull Request

A pull request is the engineering change.

It answers:

- what files changed?
- what Terraform or Ansible action will run?
- what validation passed?
- who reviewed it?

### Evidence

Evidence is the audit trail.

It answers:

- what was changed?
- when was it changed?
- who approved it?
- how was it verified?
- where is the rollback note?

## Type-Along Steps

### Step 1: Open the repo

```bash
cd /Users/sayantanchowdhury/Documents/Codex/2026-07-09/ac
git status
```

Expected idea:

- the repo should be on `main`
- it should track `origin/main`
- there should be no uncommitted changes before starting

### Step 2: Create a practice branch

```bash
git switch -c day-1-ticket-flow
```

Concept:

Every real change should happen on a branch. The branch is the safe workspace before review.

### Step 3: Copy the access request sample into a real practice ticket

```bash
cp tickets/SAMPLE_ACCESS_REQUEST.md tickets/TICKET-004-dev-readonly-access.md
```

Concept:

This simulates a requester asking for temporary read-only access. We are not granting AWS access yet. We are learning intake quality first.

### Step 4: Edit the ticket

Open:

```text
tickets/TICKET-004-dev-readonly-access.md
```

Update these fields:

- requester
- business reason
- risk level
- rollback plan
- verification

Concept:

Bad tickets cause bad changes. Good CloudOps work starts by forcing unclear requests to become clear.

### Step 5: Create evidence placeholder

```bash
cp evidence/README.md evidence/TICKET-004-evidence.md
```

Concept:

Evidence starts before the change. In real teams, this prevents "we changed it but forgot what happened."

### Step 6: Review what changed

```bash
git diff
```

Concept:

Before asking for review, always inspect your own change. This is the first quality gate.

### Step 7: Commit the ticket

```bash
git add tickets/TICKET-004-dev-readonly-access.md evidence/TICKET-004-evidence.md
git commit -m "Add day 1 access request ticket"
```

Concept:

A commit is a small, named unit of work. The message should explain what changed, not how tired we were.

### Step 8: Push the branch

```bash
git push -u origin day-1-ticket-flow
```

Concept:

Pushing makes your local branch visible in GitHub so a pull request can be opened.

### Step 9: Open a pull request

```bash
gh pr create --title "Day 1 access request ticket" --body "Adds a practice access request ticket and evidence placeholder."
```

Concept:

In real CloudOps, the PR is where review, approval, and automation checks live.

## Day 1 Success Criteria

You are done with Day 1 when:

- one practice ticket exists
- one evidence file exists
- the ticket is committed on a branch
- a pull request exists
- you can explain the difference between ticket, PR, and evidence

## Speakable Interview Answer

In my CloudOps practice project, I modeled operational requests as tickets. Each ticket includes business reason, environment, affected resources, risk, rollback, and evidence. The implementation happens through a pull request so the change can be reviewed, validated, and audited before execution.
