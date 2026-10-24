# Runbook: Purging Sensitive Data and Large Files from Git History

When a sensitive API key or a large binary file is accidentally committed to a remote branch, simply deleting the file in a new commit is insufficient—it remains stored in Git's historical object database.

## Procedure

1. **Isolate a Fresh Clone**
   Always perform history rewriting on a fresh, temporary clone to avoid corrupting active working directories:
   ```bash
   git clone <repository-url> temp-repo
   cd temp-repo
