# php/Dockerfile
FROM php:8.2-fpm

# Installation des dépendances système
RUN apt-get update && apt-get install -y \
    git \
    curl \
    libpng-dev \
    libonig-dev \
    libxml2-dev \
    zip \
    unzip

# Nettoyage du cache
RUN apt-get clean && rm -rf /var/lib/apt/lists/*

# Installation des extensions PHP
RUN docker-php-ext-install pdo_mysql mbstring exif pcntl bcmath gd

# Installation de Composer
COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

# Configuration des permissions pour www-data
RUN mkdir -p /home/www-data/.composer && \
    chown -R www-data:www-data /home/www-data && \
    chmod -R 755 /home/www-data

# Installation de Xdebug
RUN pecl install xdebug && docker-php-ext-enable xdebug

# Définition du répertoire de travail
WORKDIR /var/www/html

# Utilisation de l'utilisateur www-data
USER www-data