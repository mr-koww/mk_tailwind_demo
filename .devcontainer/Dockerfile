FROM mcr.microsoft.com/vscode/devcontainers/base:ubuntu

# Update and install dependencies
RUN apt-get update && apt-get -y install curl gnupg2

# Устанавливаем RVM зависимости и импортируем ключи
RUN curl -sSL https://rvm.io/mpapis.asc | gpg2 --import - && \
    curl -sSL https://rvm.io/pkuczynski.asc | gpg2 --import -

# Устанавливаем RVM
RUN curl -sSL https://get.rvm.io | bash -s stable

# Настраиваем окружение RVM и устанавливаем Ruby 3.2.3
RUN /bin/bash -l -c ". /etc/profile.d/rvm.sh && rvm install 3.2.3"

ENTRYPOINT ["/bin/bash", "-l", "-c"]
