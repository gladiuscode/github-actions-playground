# Pull request code checks

When a new pull request is opened against the main branch, it is a good idea to run some checks on the code to make sure
that it is up to the standards of the project.
You can run it on every push, but it is better to run it only when a pull request is approved, to avoid reaching the
limits of the Github Actions free tier.

Take a look at the following example:

```yaml

name: pull-request-code-checks

on:
  # (1) Run the workflow only when a pull request is:
  # - opened against the main branch
  # - and a review is submitted
  pull_request_review:
    branches:
      - main
    types: [ submitted ]

jobs:
  build:
    name: Build
    runs-on: ubuntu-latest

    steps:
      - name: Checkout
        uses: actions/checkout@v4

      - name: Setup
        uses: ./.github/actions/setup

      - name: Build
        run: yarn build

  lint:
    name: Lint
    runs-on: ubuntu-latest

    steps:
      - name: Checkout
        uses: actions/checkout@v4

      - name: Setup
        uses: ./.github/actions/setup

      - name: Lint
        run: yarn lint

```

