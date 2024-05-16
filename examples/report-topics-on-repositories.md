# Report Topics on Repositories

## Minimum Requirements

- A subscribing repository must have Webhook Actions installed and must include
  the `.github/webhook-actions/config.json`.
    - Alternatively you can use the `webhook-actions-config` `repositories.json` to configure the repository.
- All repositories that you want to report on must also have Webhook Actions installed. This is a GitHub limitation. It
  is not possible to subscribe to events from a repository that does not have Webhook Actions installed, as it allows
  the permissions.

## Usage

We have 4 repositories in this example:

1. `webhook-actions-config`
2. `subscriber-repo`
3. `report-repo-1`
4. `report-repo-2`

First we must install Webhook Actions on all of the above repositories. Then we must set the configuration in the
`webhook-actions-config` repository.

**Note:** *The following may not be practical for readability as your configuration grows. You may want to consider
using some templating mechanism to generate your configuration.*

```yaml
# repositories.json
# This looks for when topic-1 or topic-2 are added to a repository.
{
  "subscriber-repo": {
    "events": {
      "repository_edited": {
        "filter": {
          "$or": [
            {
              "$and": [
                {
                  "changes.topics.from": {
                    "$not": {
                      "$elemMatch": {
                        "$eq": "topic-1"
                      }
                    }
                  }
                },
                {
                  "repository.topics": {
                    "$elemMatch": {
                      "$eq": "topic-1"
                    }
                  }
                }
              ]
            },
            {
              "$and": [
                {
                  "changes.topics.from": {
                    "$not": {
                      "$elemMatch": {
                        "$eq": "topic-2"
                      }
                    }
                  }
                },
                {
                  "repository.topics": {
                    "$elemMatch": {
                      "$eq": "topic-2"
                    }
                  }
                }
              ]
            }
          ],
        },
        "map": {
          "repository": "${{ repository.name }}"
        }
      }
    }
  }
}
```

Now we can configure a GitHub Action workflow, in the `subscriber-repo`, to report on the repositories that have had
their
topics updated.

```yaml
name: Report

on:
  repository_dispatch:
    types:
      - repository_edited

jobs:
  report:
    runs-on: ubuntu-latest
    env:
      PAYLOAD: ${{ toJSON(github.event.client_payload) }}
    steps:
      - name: Report
        # Do something with the payload
        run: |
          echo $PAYLOAD
``` 
