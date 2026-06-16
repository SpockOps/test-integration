---
description: Dummy beta-k deploy readiness check.

on:
  workflow_dispatch:

permissions:
  contents: read

engine: claude

network:
  allowed:
    - defaults
    - api.anthropic.com

tools:
  github:
    lockdown: false
    min-integrity: none

safe-outputs:
  create-issue:
    title-prefix: "[deploy-readiness] "
    labels: [deployment, beta-k]

environment: beta-k
---

# Beta-K Deploy Readiness

Check recent commits to main and create an issue summarising what would deploy to beta-k.
