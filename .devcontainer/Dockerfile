FROM mcr.microsoft.com/devcontainers/ruby:3.3-bookworm

# Install system dependencies for Workato SDK and charlock_holmes
RUN apt-get update && apt-get install -y \
    build-essential \
    libicu-dev \
    libmagic-dev \
    cmake \
    pkg-config \
    libssl-dev \
    libxml2-dev \
    libxslt1-dev \
    libcurl4-openssl-dev \
    libffi-dev \
    libyaml-dev \
    && rm -rf /var/lib/apt/lists/*

# Pre-install problematic gems globally
RUN gem install charlock_holmes -v '0.7.7' && \
    gem install workato-sdk && \
    gem install workato-connector-sdk

# Set up bundler config for better performance
RUN bundle config set --global jobs 4 && \
    bundle config set --global retry 3
