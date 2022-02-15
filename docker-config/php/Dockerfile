ARG PHP_VERSION
ARG USER
ARG UID

FROM php:${PHP_VERSION}-fpm

# Install sys dependencies
RUN apt-get update && apt-get install -y \
    git \
    curl \
    libpng-dev \
    libonig-dev \
    libxml2-dev \
    zip \
    unzip

# clean cache
RUN apt-get clean && rm -rf /var/lib/apt/lists/*

# Install php dependencies
RUN docker-php-ext-install pdo_mysql mbstring exif pcntl bcmath gd

# Install composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# Create system user to run Composer & Artisan commands
# RUN useradd -G www-data,root -u $UID -d /home/$USER $USER
# RUN mkdir -p /home/$USER/.composer && \
#     chown -R $USER:$USER /home/$USER

# USER $USER
