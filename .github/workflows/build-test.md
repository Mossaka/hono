---
name: Build and Test
on:
  push:
    branches: [main]
  pull_request:
    branches: [main]
  workflow_dispatch:

permissions:
  contents: read
  issues: read
  pull-requests: read

engine:
  id: copilot
  model: claude-sonnet-4

network:
  firewall: true
  allowed:
    - defaults
    - github
    - bun
---

# Build and Test Hono

You are a CI/CD agent. Your job is to build and test this Bun-based project.

## Steps

1. Install dependencies using Bun:
   ```
   bun install
   ```

2. Run the Bun-specific test suite:
   ```
   bun run test:bun
   ```

3. Report the results - if tests pass, indicate success. If they fail, analyze the error output and report what went wrong.
