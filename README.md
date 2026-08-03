# ebpm-index

The starter package index for `ebpm` (eBasic's package manager) -
https://github.com/yann64/ebasic.

## Format

One TOML file per package, named `<name>.toml`:

```toml
[package]
name = "..."
description = "..."

[[versions]]
version = "1.0.0"
git = "https://github.com/..."
tag = "v1.0.0"   # or branch = "..." / rev = "..."

[[versions]]
version = "1.1.0"
git = "https://github.com/..."
tag = "v1.1.0"
```

`ebpm` resolves this repository's URL via, in priority order: the
`EBASIC_INDEX_URL` environment variable, `~/.ebpm/config.toml`'s
`[registry] index = "..."`, or this repository's own URL as the hardcoded
default.

## Adding a package

Add a new `<name>.toml` file (or a new `[[versions]]` entry to an existing
one) and open a pull request. There is no publish/yank tooling yet - a
maintainer edits this repository by hand, the same way an early Cargo
git-index or a Homebrew tap works.
