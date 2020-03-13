We have [good first issues][good-first-issue] for new contributors and [help
wanted][help-wanted] issues for our other contributors.

- `good first issue` has extra information to help you make your first contribution.
- `help wanted` are issues suitable for someone who isn't a core maintainer.

Maintainers will do their best to regularly make new issues for you to solve and
then help out as you work on them. 💖

# Philosophy

PRs are most welcome!

- If there isn't an issue for your PR, please make an issue first and explain
  the problem or motivation for the change you are proposing. When the solution
  isn't straightforward, for example "Implement missing command X", then also
  outline your proposed solution. Your PR will go smoother if the solution is
  agreed upon before you spend a lot of time implementing it.
  - It's OK to submit a PR directly for problems such as misspellings or other
    things where the motivation/problem is unambiguous.
- If you aren't sure about your solution yet, put WIP in the title or open as a
  draft PR so that people wait for you to finish before reviewing.
- Try to keep your PRs to a single task. Please don't tackle multiple things in
  a single PR if possible. Otherwise, grouping related changes into commits will
  help us out a bunch when reviewing!
- We encourage "follow-on PRs". If the core of your changes are good, and it
  won't hurt to do more of the changes later, we like to merge early, and keep
  working on it in another PR so that others can build on top of your work.

When you're ready to get started, we recommend the following workflow:

```
$ make build test lint
```

[good-first-issue]: https://github.com/search?q=org%3Acnabio++label%3A%22good+first+issue%22+state%3Aopen&type=Issues
[help-wanted]: https://github.com/search?q=org%3Acnabio++label%3A%22help+wanted%22+state%3Aopen&type=Issues

# Cutting a Release

When you are asked to cut a new release, here is the process:

1. Figure out the correct version number, we follow [semver](semver.org):
    * Bump the major segment if there are any breaking changes.
    * Bump the minor segment if there are new features only.
    * Bump the patch segment if there are bug fixes only.
    * Bump the build segment (version-prerelease.BUILD) if you only
      fixed something in the build, but the final binaries are the same.

1. Ensure that the master CI build is passing, then make the tag and push it.

   ```
   git checkout master
   git pull
   git tag VERSION -a -m ""
   git push --tags
   ```
