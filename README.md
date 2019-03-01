# crds-secrets

This repo is a collection of custom regex patterns that can be used to identify any private api keys, tokens or other sensitive values within a Git repository, prior to commit. When coupled with [awslab/git-secrets](https://github.com/awslabs/git-secrets), we can notify a developer of any sensitive values before adding them to the history of a project.

## Supported Patterns

| Service                     | Example Key                                                            |
| --------------------------- | ---------------------------------------------------------------------- |
| Contentful Management Token | CFPAT-322e252382f3378e22371392e7275c8ffd9cd435b98e6a03f0f177cd3011ca58 |
| Google Cloud Platform       | 796e2816844c5baad2-31c3141f7d8cc8d52ac0                                |
| Azure                       | de8fa436-51d7-01d9-50b7-4d5a2395a713                                   |
| FormIO                      | fCgFTOgWz7jiwKk3T5yXYolkuxLiVK                                         |

## Installation

After you install `git-secrets` you need to add our custom patterns as a new "provider" like so, where the path to `crds-secrets/patterns` reflects your environment...

```
git secrets --add-provider -- cat path/to/crds-secrets/patterns
```

Once done, the relative path to `patterns` will be reflected in `.git/config` and will be parsed on every commit. Please refer to that project's documentation on whitelisting values, etc.

## License

This project is licensed under the [3-Clause BSD License](https://opensource.org/licenses/BSD-3-Clause).
