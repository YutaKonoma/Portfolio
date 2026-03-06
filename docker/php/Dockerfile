# ベースイメージを指定
FROM php:8.3-fpm

# 作業ディレクトリ
WORKDIR /var/www/backend

# システム依存パッケージのインストール
RUN apt-get update && apt-get install -y \
    git \
    curl \
    libpng-dev \
    libonig-dev \
    libxml2-dev \
    zip \
    unzip \
    libzip-dev

# PHP拡張のインストール
RUN docker-php-ext-install pdo_mysql mbstring exif pcntl bcmath gd zip

# Composerのインストール
COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

# RUN apt-get update && apt-get upgrade -y && \
#   apt-get install -y libpng-dev libjpeg-dev libfreetype6-dev zip git unzip && \
#   docker-php-ext-configure gd --with-freetype --with-jpeg && \
#   docker-php-ext-install gd pdo pdo_mysql && \
#   apt-get clean && \
#   rm -rf /var/lib/apt/lists/*