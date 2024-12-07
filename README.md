# celsiusnarhwal/tag-action-release

Whenever you push a [semver](https://semver.org) tag, this GitHub Action will automatically tag the associated commit with the matching major
and minor versions. For example, if you push the tag `v1.2.3`, this action will apply the `v1` and `v1.2` 
tags to the associated commit.

This action is intended for use in the releasing of other actions, but there's nothing forcing you to use it that way.

Tags must begin with a lowercase `v`.

## Usage

```yaml
on:
  push:
    tags:
      - v*

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


