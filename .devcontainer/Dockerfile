FROM mcr.microsoft.com/vscode/devcontainers/base:debian

# Set up the Google Cloud repository.
RUN echo "deb [signed-by=/usr/share/keyrings/cloud.google.gpg] https://packages.cloud.google.com/apt cloud-sdk main" > /etc/apt/sources.list.d/google-cloud-sdk.list \
  && curl --silent https://packages.cloud.google.com/apt/doc/apt-key.gpg | apt-key --keyring /usr/share/keyrings/cloud.google.gpg add -

# Install additional OS packages.
ARG DEBIAN_FRONTEND=noninteractive
RUN apt update && apt install -y --no-install-recommends \
  python3-pip \
  google-cloud-sdk

# Install Python packages needed by the container (not the package).
RUN pip install \
  pre-commit \
  pipenv
