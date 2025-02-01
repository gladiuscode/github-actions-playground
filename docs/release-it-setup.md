# Release It Setup

This document describes how to set up [release-it](https://github.com/release-it/release-it) to run in a Github Actions workflow.

## Prerequisites

- You have installed [release-it](https://github.com/release-it/release-it) in your project;
- You have a `release` script in your `package.json` that runs `release-it` with --ci flag;

Depending on your repository settings, you may need to set up a [Github App](https://docs.github.com/en/apps/creating-github-apps/about-creating-github-apps/about-creating-github-apps) 
to create a token that allows release-it to push on main, bypassing the branch protection rules that require pull requests.
The Github App needs to be installed on the repository and have the `Contents`, `Actions` and `Administration` permissions
to properly work.

If you need to publish to npm too, you need to create an automation token to authenticate with npm and bypass the 2FA
requirement. You can create an automation token directly in the [npm website](https://www.npmjs.com/).

## Available Workflows

### release-it-without-pr-only

This workflow showcases how to set up release-it on a repository with an unprotected main branch. It doesn't require any
particular setup, as the GITHUB_TOKEN, with content permissions set to write, is enough to push to the main branch.

Take a look at the workflow here: [.github/workflows/release-it-without-pr-only.yml](../.github/workflows/release-it-without-pr-only.yml)

### release-it-with-pr-only

This workflow showcases how to set up release-it on a repository with a ruleset that only allows PRs to the main branch.
It needs a GitHub App added to the bypass list of the ruleset and a token created by the GitHub App to push to the 
main branch using the [actions/create-github-app-token](https://github.com/actions/create-github-app-token) action.
This token is then used to checkout the main branch and push the changes made by release-it.

Before running this workflow, you need to add both the GitHub App id and private key secrets to your repository with the
values associated with the GitHub App you created.

> [!IMPORTANT]
> If you are using this workflow in a repository owned by an organization, you need to create an organization-wide GitHub
> App.

Take a look at the workflow here: [.github/workflows/release-it-with-pr-only.yml](../.github/workflows/release-it-with-pr-only.yml)

### release-it-with-npm-and-pr-only

This workflow is an extension of the `release-it-with-pr-only` workflow that also publishes the package to npm. It 
requires an automation token created in the npm website to authenticate with npm and bypass the 2FA requirement.
It leverages the upload-artifact and download-artifact actions to pass additional build artifacts that needs to be
published as well, like the `build` folder.

Before running this workflow, you need to add the `NPM_ACCESS_TOKEN` secret to your repository with the value of the 
automation token.

Take a look at the workflow here: [.github/workflows/release-it-with-npm-and-pr-only.yml](../.github/workflows/release-it-with-npm-and-pr-only.yml)
