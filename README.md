# example-update-checksum-public

Example of auto update aqua-checksums.json in CI (For OSS version)

## What's the difference from aquaproj/example-update-checksum?

If you want to set up GitHub Actions for private repositories, please see [aquaproj/example-update-checksum](https://github.com/aquaproj/example-update-checksum).
This repository is based on aquaproj/example-update-checksum, but we fixed workflows to support a pull request from a fork.

* secrets aren't used if a pull request is from fork repository

In case of a pull request from a fork, basically secrets are unavailable and [`github.token` doesn't have a write permission](https://docs.github.com/en/actions/security-guides/automatic-token-authentication#permissions-for-the-github_token).

Even if a pull request is from fork, we can use secrets by [pull_request_target](https://securitylab.github.com/research/github-actions-preventing-pwn-requests/), but pull_request_target is a bit danger and if there is a vulnerability an attacker may be able to abuse your secrets.
So in this example we don't use `pull_request_target`.

## LICENSE

[MIT](LICENSE)
