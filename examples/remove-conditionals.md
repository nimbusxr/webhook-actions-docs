# Remove Conditionals
Using Webhook Actions, we can clean up workflows that use conditionals on github event payload data. One example is when we wish 
to trigger a workflow only if a pull request has been merged. A typical implementation might look like the following:

```yaml
name: Merged Pull Request

on:
  pull_request:
    types:
      - closed

jobs:
  notify:
    if: github.event.pull_request.merged
    runs-on: ubuntu-latest
    steps:
    - name: Checkout
      uses: actions/checkout@v3
    # ...
```

This workflow will actually trigger on pull_request closed, regardless of merge, which will result in many skipped jobs. We can do better and the 
following will explain how we achieve this without conditionals in the workflow but rather in the Webhook Actions config.

## Minimum Requirements
- The origin repository has Webhook Actions installed and must include the `.github/webhook-actions/config.json`.
  - Alternatively you can use the `webhook-actions-config` repository config.

**For the sake of this example, we will call our repository `example-repo`.**

## Usage

Because Webhook Actions shares events across your organization, you must filter the current repository name. Your config
will look as follows:

```yaml
{
  "events": {
    "pull_request_closed": {
      "filter": {
        "repository.name": "example-repo",
        "pull_request.merged": true
      }
    }
  }
}
```

Your workflow will be updated as follows:

```yaml
name: Merged Pull Request

on:
  repository_dispatch:
    types:
      - pull_request_closed

jobs:
  notify:
    runs-on: ubuntu-latest
    steps:
    - name: Checkout
      uses: actions/checkout@v3
    # ...
```

You'll notice that we are filtering inclusively pull requests that have been closed with a merge. The workflow is no longer on the hook (pun intended).
You should no longer see skipped runs. Beautiful!
