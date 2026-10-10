---
description: Print how many issues are open
on:
  workflow_dispatch:
permissions:
  contents: read
  issues: read
  copilot-requests: write      # bill Copilot to the SpockOps org (Actions token), not a personal token
engine:
  id: copilot
  model: copilot/gpt-5.4-mini  # "copilot/" prefix: sent as written, no alias swap
max-ai-credits: 50             # per-run cap ($0.50)
max-daily-ai-credits: 200
tools:
  github:
    toolsets: [issues]
---
# Open issue count

Use the GitHub tools to count the open issues in this repository (not pull requests).
Print exactly one line: `Open issues: N`.
Don't create, comment on, label or change anything.