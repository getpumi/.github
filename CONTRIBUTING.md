# Contributing to Pumi

This file applies to every repository in the getpumi organization unless a repository has its own CONTRIBUTING file. Read the repository's README and AGENTS.md before you start.

## Before you start

- For a bug, open an issue in the repository where the bug is, unless one already exists.
- For a change to how Pumi works, start in [getpumi/design](https://github.com/getpumi/design). The design repository holds the settled design and the open questions as issues. A change to the code that changes the design needs a decision there first.
- For a security problem, do not open an issue. Follow [SECURITY.md](SECURITY.md).

Everyone who takes part follows the [code of conduct](CODE_OF_CONDUCT.md).

## Pull requests

All changes are made through pull requests. A maintainer reviews each pull request, and CI must pass before it is merged. CI runs the tests, the sign-off check, the licence header check and the code quality checks for the repository.

Keep each pull request to one topic.

## Licence

Pumi is licensed under the [Apache License, Version 2.0](https://www.apache.org/licenses/LICENSE-2.0). By contributing, you agree that your contribution is licensed under the same terms (section 5 of the licence). You keep the copyright on your contribution. There is no contributor licence agreement.

### Licence headers

Every source file starts with these two lines, in the comment style of the file's language:

```
SPDX-License-Identifier: Apache-2.0
SPDX-FileCopyrightText: The Pumi Authors
```

For example, in Go:

```go
// SPDX-License-Identifier: Apache-2.0
// SPDX-FileCopyrightText: The Pumi Authors
```

CI fails a pull request that adds or changes a source file without these lines. "The Pumi Authors" means the people who appear in the repository's git history.

## Sign-off: the Developer Certificate of Origin

Pumi uses the [Developer Certificate of Origin](https://developercertificate.org/) (DCO) instead of a contributor licence agreement. By signing off a commit, you certify that you wrote the change or otherwise have the right to submit it under the project's licence.

Sign off each commit by adding a `Signed-off-by` line with your real name and email:

```
Signed-off-by: Jane Doe <jane@example.com>
```

`git commit -s` adds the line for you, using `user.name` and `user.email` from your git configuration.

CI checks every commit in a pull request. The check fails if a commit has no `Signed-off-by` line, or if the name and email in that line do not match the commit's author.

To fix a commit that is missing a sign-off:

- for the last commit: `git commit --amend -s --no-edit`
- for several commits: `git rebase --signoff main`

then push again with `git push --force-with-lease`.

## Commits written by an agent

Pumi is a framework for working with coding agents, and agents are welcome to write changes. Two rules apply.

1. **A person signs off.** An agent cannot certify the origin of a change, so the person who directs the agent reviews the change and adds their own `Signed-off-by` line. The commit's author must be that person, so that the sign-off matches the author.
2. **Name the agent.** A commit written mostly by an agent carries an `Assisted-by` trailer that names the harness and the model:

   ```
   Assisted-by: <harness> (<model>)
   Signed-off-by: Jane Doe <jane@example.com>
   ```

CI cannot tell whether an agent wrote a commit, so the `Assisted-by` trailer is not checked. It is required all the same.

## Questions

Open an issue in the repository, or in [getpumi/design](https://github.com/getpumi/design) for questions about the design.
