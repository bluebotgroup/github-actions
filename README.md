
> ⚠️ **Warning:** This is a public repository. Do not commit sensitive information, secrets, or credentials.

# Github reusable workflows and actions

Use these scripts in your repos to call common workflows and actions.

### Semantic Release

To use the semantic release workflow in your repository, add a job to your workflow file:

```yaml
name: Release

on:
  push:
    branches:
      - main

jobs:
  semantic-release:
    uses: bluebotgroup/github-actions/.github/workflows/semantic-release.yaml@main
    secrets:
      GH_PAT: ${{ secrets.GH_PAT }}
```

This will:
- Run semantic release on pushes to the main branch
- Send Slack notifications with the repository name and version
- Use the organization secret `GH_PAT` that belongs to the `bluebot-gh-deploys` Github user
