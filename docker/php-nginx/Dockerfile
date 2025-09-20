FROM php:8.3-fpm

# Install system dependencies
RUN apt-get update && apt-get install -y \
    nginx \
    libzip-dev \
    zip \
    unzip \
    git \
    curl \
    libonig-dev \
    libxml2-dev \
    && docker-php-ext-install pdo_mysql

# Copy Nginx config
COPY default.conf /etc/nginx/sites-available/default

# Set working directory
WORKDIR /var/www/html

# Expose port
EXPOSE 80

# Start PHP-FPM and Nginx
CMD service nginx start && php-fpm
