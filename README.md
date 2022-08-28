# Sync Fork

Github action to sync your Forks.
This action automatically sync your upstream fork.


You need to fill in the `owner` and `name` of the forked repository.

*Exemple:* https://github.com/biglinux/bigbashview

owner: biglinux

repo: bigbashview

If your fork name is identical to the upstream one, you can use ${{ github.event.repository.name }}

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
        with:
          owner: biglinux
          repo: ${{ github.event.repository.name }}
```
