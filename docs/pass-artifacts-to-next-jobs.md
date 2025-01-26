# Pass artifacts to next jobs

When you have a workflow with multiple jobs and you need to pass artifacts (products) from one job to the next ones,
you can use the `needs` keyword and a couple of actions from the GitHub Marketplace.

The `needs` keyword allows you sequence the jobs in a workflow. You can specify that a job can only run after another 
job has completed successfully. This is required when you need to pass artifacts from one job to another.

To actually pass the artificats, you can use the `upload-artifact` and `download-artifact` actions from the GitHub
Marketplace. The `upload-artifact` action allows you to upload a file or directory as an artifact. The `download-artifact`
action allows you to download an artifact from a previous job.

Take a look at the following example:

```yaml

name: pass-artifacts-to-next-jobs

on: workflow_dispatch

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

      - name: Upload Build Artifact
        uses: actions/upload-artifact@v4
        with:
          name: build-artifact
          path: build

  run-build:
    name: Run build
    runs-on: ubuntu-latest
    needs: build

    steps:
      - name: Checkout
        uses: actions/checkout@v4

      - name: Setup
        uses: ./.github/actions/setup

      - name: Download Build Artifact
        uses: actions/download-artifact@v4
        with:
          name: build-artifact

      - name: Run
        # This assumes that your build artifacts is an index.js
        run: node index.js

```
