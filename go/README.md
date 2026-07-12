# go

This development container includes:
- Go 1.26
- golangci-lint
- GitHub CLI
- Claude Code

Based on the official Go Alpine image, it installs common command-line tools and
uses a non-root `vscode` user with zsh as the default shell.

## Build

Build the `latest` image with:

```sh
make
```

Build the `verify` image with:

```sh
make verify
```

Both targets build for `linux/amd64`. See the [`Dockerfile`](Dockerfile) for
the installed tools and the [`Makefile`](Makefile) for the available image
targets.

The explicit platform keeps the image architecture consistent and lets Docker
use emulation when building or running it on an arm64 host.
