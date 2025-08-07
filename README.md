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
    with:
      repo: ${{ github.repository }}
    secrets: inherit
```

This will:
- Run semantic release on pushes to the main branch
- Allow manual triggering with optional dry-run mode
- Send Slack notifications with the repository name and version
- Inherit all necessary secrets from your repository
