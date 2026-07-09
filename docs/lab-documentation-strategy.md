---
title: Lab Documentation Strategy
---

# Lab Documentation Strategy

GitHub Pages is not mandatory for every lab, but it is useful when the lab should be presented, reviewed, or revisited later.

## Use GitHub Pages When

- the lab has multiple days or modules
- you want a clean landing page
- you want to show the project to an interviewer
- the repo has many folders
- the lab has architecture diagrams or runbooks
- you want notes to be readable without cloning the repo

## Skip GitHub Pages When

- the lab is a tiny one-file experiment
- the repo is private scratch work
- the README is already enough
- the project will be deleted quickly

## Recommended Pattern

For serious practice labs:

- keep `README.md` as the repo overview
- keep `docs/` as the Pages website
- keep daily guides under `syllabus/`
- keep operational runbooks under `docs/`
- link issues, PRs, and evidence from the site

## Current Repo Status

This repo already has a Pages-ready `docs/` folder.

GitHub Pages activation is blocked while the repository is private unless the account plan supports Pages for private repositories.

If the repo is made public, Pages can be enabled from:

```text
Settings -> Pages -> Build and deployment -> Source: Deploy from a branch -> main / docs
```

## Why This Helps

In interviews, a Pages site lets you say:

"I documented the lab as an internal engineering portal, with links to tickets, workflows, runbooks, and implementation areas."
