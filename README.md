# Lorekeeper Docs

This is the home of core documentation for the [Lorekeeper](https://github.com/lk-arpg/lorekeeper) project, built using [mkdocs-material](https://squidfunk.github.io/mkdocs-material/).

The copy of the documentation currently being worked on can be found in the `docs` directory. This corresponds to the documentation for the **upcoming release of Lorekeeper** (the current release branch, e.g. `release/v3.0.0`), *not* the current stable release **or** the contents of the `develop` branch.

## Contributing

All of the documentation files contained herein are markdown; it should be possible to make changes to the documentation simply by editing the relevant files. However, it is recommended to preview how your changes will look as you make them.

Note: **Do not** make changes to anything on the `gh-pages` branch unless explicitly directed to! Deploying new versions of the docs to this branch is handled automatically.

### Building the site

- Install [uv](https://docs.astral.sh/uv/)
- Run `uv run mkdocs serve` in the root of the repo