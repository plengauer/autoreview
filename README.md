A Github action to automatically autoreview by finding the right reviewers.

Use it like this:
```yaml
name: Autoreview

on:
  pull_request:
    types: [ opened, reopened, synchronize, ready_for_review ]

jobs:
  review:
    runs-on: ubuntu-slim
    permissions:
      pull-requests: write
    steps:
      - uses: plengauer/autoreview@main # TODO pin to a version if needed
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }} # TODO token for GITHUB for the user to approve the PRs with (if a custom token is used that is not the built-in token, set permissions above)
```
