FROM wordpress:php5.6-apache

RUN rm -f /etc/apache2/sites-available/000-default.conf
RUN rm -f /etc/apache2/sites-enabled/000-default.conf
ADD ./000-default.conf /etc/apache2/sites-available
RUN ln -s /etc/apache2/sites-available/000-default.conf /etc/apache2/sites-enabled/000-default.conf

# Install the mysql client or wp will have issues with sql-related commands
# Also install git.
# There seems to be a problem with using sendmail in a debian container so we
# shall install ssmtp instead.
# Also add php5-mysql
RUN apt update && apt install -y mysql-client git ssmtp php5-mysql

# This enables the ZipArchive class
RUN  docker-php-ext-install zip 

# Remove ssmtp's default config
RUN rm /etc/ssmtp/ssmtp.conf
ADD ./ssmtp.conf /etc/ssmtp/

ADD ./php.ini /usr/local/etc/php

# Give ownership of webroot to apache
RUN chown -R www-data:www-data /var/www/html

# Add WP-CLI
ADD ./wp /usr/local/bin/wp
