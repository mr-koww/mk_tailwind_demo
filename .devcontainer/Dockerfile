FROM mcr.microsoft.com/vscode/devcontainers/base:ubuntu

# Update and install dependencies
RUN apt-get update && apt-get -y install curl gnupg2

# Install RVM dependencies and import keys
RUN curl -sSL https://rvm.io/mpapis.asc | gpg2 --import - && \
    curl -sSL https://rvm.io/pkuczynski.asc | gpg2 --import -

# Install RVM
RUN curl -sSL https://get.rvm.io | bash -s stable

# Set up RVM environment and install Ruby 3.2.3
RUN bash -c "source ~/.rvm/scripts/rvm && rvm install 3.2.3 && rvm use 3.2.3 --default"

# Make RVM available for future shell sessions
RUN echo 'source ~/.rvm/scripts/rvm' >> ~/.bashrc
