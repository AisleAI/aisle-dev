ARG IMAGE=bullseye
FROM mcr.microsoft.com/devcontainers/${IMAGE}

ENV PYTHONUNBUFFERED 1

RUN python -m pip install --upgrade pip \
     && python -m pip install grpcio \
     && python -m pip install grpcio-tools

RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
     && apt-get -y install --no-install-recommends postgresql-client \
     && apt-get clean -y && rm -rf /var/lib/apt/lists/*

# Install Github CLI https://github.com/cli/cli#installation
RUN (type -p wget >/dev/null || (sudo apt update && sudo apt-get install wget -y)) \
     && sudo mkdir -p -m 755 /etc/apt/keyrings \
     && wget -qO- https://cli.github.com/packages/githubcli-archive-keyring.gpg | sudo tee /etc/apt/keyrings/githubcli-archive-keyring.gpg > /dev/null \
     && sudo chmod go+r /etc/apt/keyrings/githubcli-archive-keyring.gpg \
     && echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/githubcli-archive-keyring.gpg] https://cli.github.com/packages stable main" | sudo tee /etc/apt/sources.list.d/github-cli.list > /dev/null \
     && sudo apt update \
     && sudo apt install gh -y