# AGENTS.md

The opam repository of Hypha Stack: the opam file of every published
version of its libraries, which users add with `opam repo add` and install
from. This file is for anyone changing it, human or agent. Users start at
[README.md](README.md).

## Layout

```
repo                                   the repository's opam configuration
packages/<name>/<name>.<version>/opam  one published version of a package
.github/workflows/ci.yml               lints and installs what a change adds,
                                       and lands a release/ branch on main
```

It is served from git, so nothing is generated: `opam update` reads the
tree at `main`.

## Rules that must hold

- **A version is published by its library's release workflow, never by
  hand.** The workflow uploads the archive the checksum is taken from and
  pushes `release/<library>-<version>`, which CI checks and lands on
  `main`. Why: an opam file written by hand names an archive nobody
  uploaded, or a checksum of other bytes. Symptom: a commit on `main`
  adding a version that is not `Publish <library> <version>`.
- **A published version never changes.** Its archive, checksum and opam
  file stay as published; a mistake is fixed by the next version. The one
  exception is narrowing a bound that proved wrong. Why: a changed
  checksum fails every install that cached the old one, and a version that
  moves is not one a user can come back to. Symptom: a diff to an existing
  `<name>.<version>/opam` other than a bound.
- **Every file meets ocaml/opam-repository's policies**: no `v` in a
  version, sha256 and sha512 checksums and never md5, no extra files, no
  package that follows a branch, and an archive that is a release asset,
  never GitHub's generated `archive/` URL. Why: a version can then be
  submitted there as it is; and GitHub does not keep its generated
  archives byte for byte. Symptom: `opam lint` warns in CI, or a `src:`
  with `/archive/` in it.
- **It carries the packages of Hypha Stack and nothing else.** Why: a user
  who adds it trusts it ahead of opam's own repository, for these names
  only. Symptom: a directory under `packages/` the README's table does not
  list.

## Git

How work becomes a commit -- its format, where it happens, what is pushed
-- is [GIT.md](GIT.md), the same in every Hypha repository and changed in
all of them together, never in one. It is imported here, so it is read
with this file:

@GIT.md

A `release/` branch is the one exception to *Work lands locally*: its
commit is written by a library's release workflow and landed by this
repository's CI.
