FROM mcr.microsoft.com/devcontainers/python:3.12-bullseye

# Install additional tools for development
RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
    && apt-get -y install --no-install-recommends \
        curl \
        git \
        vim \
        nano \
        htop \
        postgresql-client \
        docker.io \
        docker-compose \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

# Install Node.js (for any frontend development)
RUN curl -fsSL https://deb.nodesource.com/setup_lts.x | bash - \
    && apt-get install -y nodejs

# Install Python development tools
RUN pip install --no-cache-dir \
    black \
    ruff \
    pytest \
    mypy \
    jupyter \
    ipython \
    requests \
    httpx \
    python-dotenv

# Set up workspace
WORKDIR /workspaces/groundedllm

# Keep container running
CMD ["sleep", "infinity"]