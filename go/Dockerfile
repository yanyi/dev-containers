# Use the official Go image as base
FROM golang:1.24-alpine

# Install essential packages and golangci-lint from Alpine packages
# git-delta package info: https://pkgs.alpinelinux.org/packages?name=delta&branch=v3.22
RUN apk add --no-cache \
    bash \
    curl \
    vim \
    nano \
    git \
    fzf \
    jq \
    just \
    zsh \
    man-db \
    golangci-lint \
    delta \
    nodejs \
    npm

# Install gh (GitHub CLI) from official GitHub release
RUN wget -qO- https://github.com/cli/cli/releases/download/v2.76.2/gh_2.76.2_linux_amd64.tar.gz | \
    tar -xzf - && \
    mv gh_2.76.2_linux_amd64/bin/gh /usr/local/bin/ && \
    chmod +x /usr/local/bin/gh && \
    rm -rf gh_2.76.2_linux_amd64*

# Install Claude Code
RUN npm install -g @anthropic-ai/claude-code

# Create a non-root user with zsh as default shell
RUN adduser -D -s /bin/zsh vscode
# Set user
USER vscode

# Set working directory
WORKDIR /workspace

# Set zsh as default shell
ENV SHELL=/bin/zsh
