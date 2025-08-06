FROM ghcr.io/gleam-lang/gleam:v1.12.0-erlang-slim

# Install essential packages
RUN apt-get update && apt-get install -y \
    wget \
    bash \
    curl \
    vim \
    nano \
    git \
    fzf \
    jq \
    zsh \
    man-db \
    delta \
    build-essential \
    unzip && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

# Install Just
RUN curl --proto '=https' --tlsv1.2 -sSf https://just.systems/install.sh | \
    bash -s -- --to /usr/local/bin

# Install Node.js
RUN curl -fsSL https://deb.nodesource.com/setup_lts.x | bash - && \
    apt-get install -y nodejs && \
    apt-get autoremove -y && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

# Install Bun
RUN curl -fsSL https://bun.com/install | bash

# Install gh (GitHub CLI) from official GitHub release
RUN wget -qO- https://github.com/cli/cli/releases/download/v2.76.2/gh_2.76.2_linux_amd64.tar.gz | \
    tar -xzf - && \
    mv gh_2.76.2_linux_amd64/bin/gh /usr/local/bin/ && \
    chmod +x /usr/local/bin/gh && \
    rm -rf gh_2.76.2_linux_amd64*

# Create a non-root user with zsh as default shell
RUN useradd -m -s /bin/zsh vscode
USER vscode

# Set working directory
WORKDIR /workspace

# Set zsh as default shell
ENV SHELL=/bin/zsh
