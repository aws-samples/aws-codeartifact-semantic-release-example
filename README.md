# AWS CodeArtifact Semantic Release Example

## Summary

This pattern shows how to integrate [semantic-release][semantic-release] into
your project to automate the entire package release workflow of determining the
next version number, generating release notes, and publishing the package to
[AWS CodeArtifact][codeartifact].

In this example, we will be using GitHub with semantic-release to automate the
release workflow of an npm package.

## Prerequisites and Limitations

### Prerequisites

- An active [AWS account][create-aws-account].
- An [AWS CodeArtifact][codeartifact] repository.
- A [GitHub][github] repository.
- [Node.js][nodejs] v14.x or later on developer machines.

### Limitations

- The [semantic-release-coderatifact][semantic-release-codeartifact] plugin
currently only supports npm at the time of writing.

## Architecture

![Architecture Image][architecture-img]

The diagram shows the following workflow:

1. Developers commit changes to the GitHub repository following a standardized
commit message format (enforced by [commitizen][commitizen]).

1. The GitHub Action [release workflow][release-workflow] assumes the IAM role
for publishing to CodeArtifact.

1. The npm package is published to the CodeArtifact repository.

## Tools

- [AWS CodeArtifact][codeartifact] - Fully managed artifact repository service.
- [GitHub Actions][github-actions] - Runs release workflow.
- [semantic-release][semantic-release] - Used to automate the package release workflow.
- [semantic-release-codeartifact][semantic-release-codeartifact] - Plugin for AWS CodeArtifact.
- [commitizen][commitizen] - Command line utility to help standardize commit messages.
- [husky][husky] - Adds git hooks we use for automatically running commitizen on commit.

## Best Practices

## Related Resources

- [Semantic Release: How does it work?][semantic-release-how-does-it-work]

## Security

See [CONTRIBUTING](CONTRIBUTING.md#security-issue-notifications) for more information.

## License

This library is licensed under the MIT-0 License. See the LICENSE file.

[architecture-img]:./docs/img/architecture.svg
[codeartifact]:https://aws.amazon.com/codeartifact
[commitizen]:https://github.com/commitizen/cz-cli
[create-aws-account]:https://aws.amazon.com/premiumsupport/knowledge-center/create-and-activate-aws-account/
[github-actions]:https://docs.github.com/en/actions
[github]:https://github.com
[husky]:https://www.npmjs.com/package/husky
[nodejs]:https://nodejs.org/en/download/
[release-workflow]:./.github/workflows/release.yml
[semantic-release-codeartifact]:https://www.npmjs.com/package/semantic-release-codeartifact
[semantic-release]:https://github.com/semantic-release/semantic-release
[semver]:https://semver.org/
[semantic-release-how-does-it-work]:https://github.com/semantic-release/semantic-release#how-does-it-work
