FROM debian:latest

WORKDIR /app

COPY . .

RUN apt-get update && apt-get install -y \
    curl \
    git \
    build-essential \
    bash \
    && rm -rf /var/lib/apt/lists/*

RUN curl -sL https://deb.nodesource.com/setup_18.x | bash - && \
    apt-get install -y nodejs && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*