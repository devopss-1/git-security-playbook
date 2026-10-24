---

###  `docs/02-pre-commit-hooks.md`

```markdown
# Guide: Shift-Left Security with Pre-Commit Hooks

Waiting for CI/CD pipelines or server-side scanners to catch secrets is inefficient. Shift-left security relies on client-side hooks to block bad commits before they ever leave the developer's workstation.

## Setup Instructions

  Install the framework:
   ```bash
   brew install pre-commit  # macOS
   # or
   pip install pre-commit   # Cross-platform
