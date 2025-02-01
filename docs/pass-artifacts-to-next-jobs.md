# Pass artifacts to next jobs

This document describes how to pass artifacts from one job to the next ones.

Artifacts are the files created by a job that you want to persist after the job has completed. They may be log files or
build outputs that you want to include in a release, for example in a npm package as the product of `tsc`.

When you have a workflow with multiple jobs, and you need to pass artifacts from one job to the next ones, you need to
use the `needs` keyword to sequence your job to run after a previous one has completed and a couple of actions from the
GitHub Marketplace.

To pass the artifacts, you can use the [upload-artifact](https://github.com/actions/upload-artifact) and [download-artifact](https://github.com/actions/download-artifact)
actions from the GitHub Marketplace. The `upload-artifact` action allows you to upload a file or directory as an artifact,
while the `download-artifact`action allows you to download an artifact from a previous job.

Take a look at the workflow here: [.github/workflows/pass-artifacts-to-next-jobs.yml](../.github/workflows/pass-artifacts-to-next-jobs.yml)
