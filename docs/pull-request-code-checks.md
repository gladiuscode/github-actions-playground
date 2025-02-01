# Pull request code checks

This document explains how to run code checks on a pull request.

## Prerequisites

- You have configured the required scripts to run the checks;

When a new pull request is opened against the main branch, it is a good idea to run some checks on the code to make sure
that it is up to the standards of the project, before merging it. 

You can run it on every push, but it is better to run it only when a pull request is approved, to avoid reaching the
limits of the Github Actions free tier.

The workflow provided by this repository runs eslint and typescript checks each time someone submits a review on a pull
request.

Take a look at the workflow here: [.github/workflows/pull-request-code-checks.yml](../.github/workflows/pull-request-code-checks.yml)
