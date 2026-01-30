# GitHub Actions Workflows

## Clean up old deployments

This workflow helps clean up old GitHub deployment records, keeping only the most recent one.

### Purpose
Removes old deployment entries from the repository to keep the deployment history clean and manageable. According to the issue, there are 98 deployments and this workflow will delete 97, keeping only the most recent active one.

### How to use
1. Go to the **Actions** tab in the GitHub repository
2. Select **"Clean up old deployments"** from the workflows list
3. Click **"Run workflow"**
4. Select the branch (typically `main`)
5. Click **"Run workflow"** button

### What it does
- Lists all deployments in the repository
- Sorts them by creation date
- Keeps only the most recent deployment
- Deletes all other deployments (sets them to inactive first, then deletes)
- Includes rate limiting protection (500ms between deletions)
- Tracks and reports success/failure counts
- Fails if any deletions fail

### Important notes
- This workflow deletes deployments **across all environments**
- It requires `deployments: write` permission
- Manual trigger only (workflow_dispatch)
- The workflow will fail if any deletions fail, showing how many succeeded and failed

### Example output
```
Found 98 total deployments
Keeping deployment: 12345 (environment: github-pages, created: 2026-01-30T12:00:00Z)
Note: This will delete deployments across all environments.
Deleting 97 old deployments...
Deleted deployment 12344 (environment: github-pages)
Deleted deployment 12343 (environment: github-pages)
...
Cleanup completed: 97 deleted, 0 failed
```
