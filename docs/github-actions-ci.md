# Guide: Server-Side Enforcement via GitHub Actions

While pre-commit hooks catch secrets on the developer's workstation, server-side CI/CD pipelines act as an unbypassable safety net to protect the main branch.

## What This Workflow Does

1. **Gitleaks Scan (`gitleaks-action`)**: Clones the repository with full history (`fetch-depth: 0`) and checks every commit and pull request diff against hundreds of known secret patterns and custom regular expressions.
2. **Pre-commit Check (`pre-commit-action`)**: Automatically installs and executes the repository's `.pre-commit-config.yaml` rules (such as blocking large files >5MB, trailing whitespace, or malformed YAML) in an isolated Linux environment before merging is allowed.
