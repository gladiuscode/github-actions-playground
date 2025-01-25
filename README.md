# github-actions-playground
This repository is used as a playground to learn and mess with github actions.

## Notes

A basic workflow is configured as follows:

```yaml

name: CI

on: [push]

jobs:
  build:
    name: Build
    runs-on: ubuntu-latest

    steps:
      - name: SayHi
        run: echo "Hello, ${{ github.actor }}"

```

Each job runs in a fresh instance of the virtual environment, this means that we need to checkout the branch and install
the dependencies in each job;

Continuos Integration (CI): is the practice of automating the integration of code changes from multiple contributors 
into a single software project. The CI process is comprised of automatic tools that assert the new code’s correctness 
before integration. This means that you can set up github actions to run tests, linters, etc. on each push to the
repository or on a pull request.

Continuous Deployment (CD): is the practice of automating the deployment of code changes to a production environment.
This means that you can set up github actions to deploy your code to a server, a cloud provider, etc. once you are 
ready to release a new version of your software.

By default, github actions have got the GITHUB_TOKEN secret, which is a token that allows the action to interact with the
github API. This token is automatically created by github and is available to all actions. You can use this token to
create issues, pull requests, etc. from your actions. 
If you want to push to the repository tho, you need to update the permissions of the token and you can do it right in
the worflow file using the `permissions` key.
