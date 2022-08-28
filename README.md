# Sync Fork

Github action to sync your Forks.
This action automatically sync your upstream fork.

# Example Workflow

```yml
name: Sync Fork

on:
  schedule:
    - cron: '0 */6 * * *' # every 6 hours
  workflow_dispatch: # on button click

jobs:
  Sync:

    runs-on: ubuntu-latest

    steps:
      - uses: actions/checkout@v3
      
      - name: Sync and Push
        uses: BigLinux-Package-Build/sync-fork@main
```
