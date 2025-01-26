# Github Actions Playground

In this repository you can find templates and examples of some github actions workflows that I use in my own projects.
They are mainly focused around Typescript and React Native projects, because that's what I work with most of the time.

Feel free to copy them and use them in your own projects.

## Contributing

Contributions are welcome! If you have a workflow that you think is useful and you want to share it, feel free to open a
pull request.

## Workflows

### Release with [release-it](https://github.com/release-it/release-it)

This workflow is triggered manually and can bypass the ruleset that blocks any push to the main branch. It does it by
using a Github App that has been added to the bypass list in the branch protection rules.
Take a look at the [release-it-setup](./docs/release-it-setup.md) document to see how to set it up and an alternative
approach to the bypass procedure.

### Useful links

- [Github Actions Documentation](https://docs.github.com/en/actions)


