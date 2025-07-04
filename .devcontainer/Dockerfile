# ## pythonとNode.jsの開発環境を構築するためのDockerfile
# ARG PYTHON_VARIANT=3.12
# FROM mcr.microsoft.com/devcontainers/python:${PYTHON_VARIANT}

# Dockerfile
FROM mcr.microsoft.com/playwright:v1.51.1-jammy

# 共通依存のインストール
RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
    && apt-get install -y \
        build-essential \
        python3 \
        python3-pip \
        libzmq3-dev \
        libffi-dev \
        python3-dev \
        curl \
        wget \
        gnupg \
        bash-completion \
        ca-certificates \
        git \
    && rm -rf /var/lib/apt/lists/*
    

# ## uvをインストール
# RUN curl -LsSf https://astral.sh/uv/install.sh | sh 
# ENV PATH="/root/.cargo/bin:$PATH"

# uvをpipでインストール（システム全体で利用可能）
RUN pip install uv

# # uvをインストール
# RUN curl -LsSf https://astral.sh/uv/install.sh | sh
# ENV PATH="/root/.cargo/bin:$PATH"

# # uvが正しくインストールされているか確認し、システム全体で使用可能にする
# RUN cp /root/.cargo/bin/uv /usr/local/bin/uv && chmod +x /usr/local/bin/uv
