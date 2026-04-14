# security-workflows

Central Semgrep SAST reusable workflow. Add this to any repo in 6 lines.

## Usage

Create `.github/workflows/security.yml` in any repo:

```yaml
name: Security Scan
on:
  pull_request:

permissions:
  contents: read
  pull-requests: write

jobs:
  sast:
    uses: 4nkittt/security-workflows/.github/workflows/semgrep.yml@main
    secrets: inherit
```

## What it does

- Auto-detects language (Go, Java, Python, JS/TS, Rust)
- Runs OWASP Top 10 + secrets detection + language-specific rules
- Posts findings as inline review comments on the exact PR line
- Writes a findings table to the Actions job summary
