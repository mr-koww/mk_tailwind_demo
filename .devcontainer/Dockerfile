FROM mcr.microsoft.com/vscode/devcontainers/base:ubuntu

# use this Dockerfile to install additional tools you might need, e.g.
RUN apt-get update && apt-get -y install

# RVM
RUN curl -sSL https://rvm.io/mpapis.asc | gpg2 --import -
RUN curl -sSL https://rvm.io/pkuczynski.asc | gpg2 --import -
RUN curl -sSL https://get.rvm.io | bash -s stable

# Load RVM into the shell
RUN source ~/.rvm/scripts/rvm

# Install Ruby 3.2.3
RUN rvm install 3.2.3

# Set Ruby 3.2.3 as the default version
RUN rvm use 3.2.3 --default
