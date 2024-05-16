# Remote Repository Dispatch
Using Webhook Actions, we can dispatch events to repositories across the organization, without the use of a Personal Access Token.

## Minimum Requirements
- An origin repository has Webhook Actions installed. 
  - This is necessary for reporting repository dispatch events to Webhook Actions.
- A remote repository has Webhook Actions installed.

## Usage
Your origin repository can use a repository dispatch as follows:

```yaml
name: Remote Repository Dispatch
on:
  workflow_dispatch:
jobs:
  dispatch:
    runs-on: ubuntu-latest
    steps:
      - name: Repository Dispatch
        uses: peter-evans/repository-dispatch@v2
        with:
          event-type: remote-repository-dispatch
          client-payload: '{"description": "I am a remote repository dispatch using Webhook Actions."}'
```

Your remote repository must have a Webhook Actions configuration as follows:

```yaml
{
  "events": {
    "repository_dispatch_remote-repository-dispatch": {
      # ...
    }
  }
}
```

Then you can use in a workflow as follows:

```yaml
name: Log Webhook Dispatch

on:
  repository_dispatch:
    types:
      - repository_dispatch_remote-repository-dispatch

jobs:
  run:
    runs-on: ubuntu-latest
    env:
      PAYLOAD: ${{ toJSON(github.event.client_payload.client_payload) }}
    steps:
      - name: log event
        run: echo $PAYLOAD
```
