<!-- section-title: 5 - Designer Workflow -->

<!-- note
What does that look like for the developer?
-->
## Developer Workflow
- when a pr is opened, a [github action is triggered](https://github.com/MeowWolf/figma-tokens/blob/main/.github/workflows/build.yml) which reads the updated `tokens.json` file and generates our updated styles using [style dictionary](https://amzn.github.io/style-dictionary/#/)
- a developer(s) reviews the PR and approves/requests changes.
- upon approval, a developer adds the "version bump" label to the PR.
- adding the "version bump" label [triggers a github action](https://github.com/MeowWolf/figma-tokens/blob/main/.github/workflows/bump.yml) which issues a git release tag and bumps the `package.json` version.
- a developer creates a release from the latest tag in github.
- Creating a release from the tag in github [triggers another github action](https://github.com/MeowWolf/figma-tokens/blob/main/.github/workflows/publish.yml) which publishes a release to NPM.
- a developer updates all applications that use `figma-tokens` as a dependency.
