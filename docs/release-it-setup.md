## If you allow direct pushes to the main branch

```yaml

name: release

on: workflow_dispatch

jobs:

  release:
    name: Release
    runs-on: ubuntu-latest
    needs: build

    # (1) Give GIT_TOKEN permission to push to the repository
    # By default, the GITHUB_TOKEN does not have permission to push to the repository
    permissions:
      contents: write

    steps:
      - name: Checkout
        uses: actions/checkout@v4

      # This is a custom action that sets up the environment
      - name: Setup
        uses: ./.github/actions/setup

      # (2) Configure a git user to make the release
      # This is required to identify the user
      - name: Configure Git User
        run: |
          git config --global user.name "${GITHUB_ACTOR}"
          git config --global user.email "${GITHUB_ACTOR}@users.noreply.github.com"

      - name: Release
        run: yarn release
        env:
          # (3) Provide the GITHUB_TOKEN to release-it
          # This is required to identify the user who made the release
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}

```

## If you don't allow direct pushes to the main branch

You need to create a GitHub App and add it to the bypass list in your rules. 
See [here](https://github.com/orgs/community/discussions/13836#discussioncomment-8535364)

```yaml

name: release

on: workflow_dispatch

jobs:

  release:
    name: Release
    runs-on: ubuntu-latest
    needs: build

    steps:
      # (1) This action creates a token using the GitHub App
      - uses: actions/create-github-app-token@v1
        id: app-token
        with:
          # (1.1) Provide the App ID and Private Key
          # Be sure to read the private key value from the .pem file that you downloaded from the GitHub App web page
          # upon private key creation. (Not the SHA that you see in the GitHub App web page!!)
          app-id: ${{ vars.APP_ID }}
          private-key: ${{ secrets.PRIVATE_KEY }}
    
      - name: Checkout
        uses: actions/checkout@v4
        with:
          # (2) Tell checkout to use the token created by the GitHub App
          token: ${{ steps.app-token.outputs.token }}

      # This is a custom action that sets up the environment
      - name: Setup
        uses: ./.github/actions/setup

      # (3) Configure a git user to make the release
      # This is required to identify the user
      - name: Configure Git User
        run: |
          git config --global user.name "${GITHUB_ACTOR}"
          git config --global user.email "${GITHUB_ACTOR}@users.noreply.github.com"
    
      - name: Release
        run: yarn release
        env:
          # (4) Provide the GITHUB_TOKEN to release-it but use the token created by the GitHub App
          # This is required to identify the user who made the release
          GITHUB_TOKEN: ${{ steps.app-token.outputs.token }}

```



