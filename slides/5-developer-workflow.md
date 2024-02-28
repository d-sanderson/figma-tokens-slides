## Developer Workflow
- when a pr is opened, a github action is triggered which examines the updates tokens.json file and builds our updated css using [style dictionary](https://amzn.github.io/style-dictionary/#/)
- a developer(s) reviews the PR and approves/requests changes.
- upon approval, a developer adds the "version bump" label to the PR.
- adding the 'version bump' label triggers a github action which adds a git release tag and bumps the version.
- a developer creates a release from the tag in github.
- Creating a release from the tag in github triggers a github action which publishes a release to NPM.
