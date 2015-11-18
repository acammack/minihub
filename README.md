Minihub
=======

Minihub is a tiny alternative to GitHub's [hub](https://github.com/github/hub)
client.

Usage
-----

Minihub requires `git` to be in your path and `.git/description` to be the name
of the repository. `curl` and the environment variable `GITHUB_USER=<username>`
are required to submit pull requests. It will ask for your password as needed.

```
minihub push|fetch|checkout|pull <user> <ref>
```
Push, fetch, checkout, pull to/from `<ref>` of `<user>`'s repository. Note that
checkout will put you into a detached head state, meaning you will have to
`git checkout -b <new-branch>` or cherry-pick or pull the commits to an
existing branch to be able to push any new commits you make.

```
minihub pull-request|pr <user> <basebranch> <title> <message>
```
Open a pull request from `HEAD` to `<user>/<basebranch>` with `<title>` and
`<message>`. These commits must have been previously pushed to referenced
correctly.
