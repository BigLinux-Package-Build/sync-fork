# Sync Fork

Github action to sync your Forks.
This action automatically sync your upstream fork.
You need to fill in the owner and name of the forked repository.

This action uses to automatically create and merge a pull request with the head defined by `head` into the base defined by `base`. The head branch owner is defined by `owner`. If you create a PR in the same repository you can omit the `owner` parameter.

# Example Workflow

```yml
name: Fork Sync

on:
  schedule:
    - cron: '*/30 * * * *' # every 30 minutes
  workflow_dispatch: # on button click

jobs:
  sync:

    runs-on: ubuntu-latest

    steps:
      - uses: BigLinux-Package-Build/sync-fork@main
        with:
          owner: biglinux
          repo: ${{ github.event.repository.name }}
```
