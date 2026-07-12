# elm-tailwind

This development container includes:
- Elm v0.19.2
- Tailwind CSS

Based on the VS Code JavaScript/Node.js development container image, it installs
Elm tooling and Tailwind CSS dependencies.

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

The base image is published for `linux/amd64`, while Apple Silicon Macs use
`linux/arm64`. The explicit platform keeps the image architecture consistent
and lets Docker use emulation when building or running it on an arm64 host.
