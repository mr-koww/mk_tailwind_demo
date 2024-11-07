FROM mcr.microsoft.com/vscode/devcontainers/base:ubuntu

# Update and install dependencies
RUN apt-get update && apt-get -y install curl gnupg2

# Переключаемся на пользователя gitpod_devcontainer
USER gitpod_devcontainer

# Устанавливаем RVM зависимости и импортируем ключи
RUN curl -sSL https://rvm.io/mpapis.asc | gpg2 --import - && \
    curl -sSL https://rvm.io/pkuczynski.asc | gpg2 --import -

# Устанавливаем RVM
RUN curl -sSL https://get.rvm.io | bash -s stable

# Настраиваем окружение RVM и устанавливаем Ruby 3.2.3
RUN bash -c "source ~/.rvm/scripts/rvm && \
    rvm install 3.2.3 && \
    rvm use 3.2.3 --default"

# Обеспечиваем доступность RVM в будущих сессиях
RUN echo 'source ~/.rvm/scripts/rvm' >> ~/.bashrc

# Возвращаемся к пользователю root, если необходимы дальнейшие конфигурации
USER root
