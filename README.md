# celsiusnarhwal/tag-action-release

Whenever you push a semver tag, this GitHub Action will automatically tag the associated commit with the matching major
and minor versions. For example, if you publish a release tagged`v1.2.3`, this action will apply the `v1` and `v1.2` 
tags to the associated commit.

## Usage

```yaml
on:
  release:
    types:
      - published

permissions:
  contents: write

jobs:
  release:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout Repository
        uses: actions/checkout@v4

      - name: Tag Release
        uses: celsiusnarhwal/tag-action-release@v1
```


