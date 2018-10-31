FROM debian:stretch-slim

MAINTAINER spencer@somanydoors.ca

RUN apt-get -qq update && \
	apt-get -qq install \
		php7.0 \
		php7.0-mysql \
		apache2 \
		libapache2-mod-php7.0 \
		php7.0-xml \
		php7.0-gd \
		php7.0-mbstring \
		php7.0-zip \
		php7.0-bz2 \
		php7.0-curl \
		php7.0-intl \
		php7.0-mcrypt \
		php7.0-ldap \
		php-smbclient \
		php7.0-imap \
		php7.0-gmp \
		php-apcu \
		php-imagick \
		ffmpeg \
		wget

RUN cd / && \
	wget -q https://download.nextcloud.com/server/releases/nextcloud-14.0.3.tar.bz2 && \
	cd /var/www/html && \
	tar -xjf /nextcloud-*.tar.bz2 --strip=1 && \
	rm /nextcloud-*.tar.bz2

CMD apachectl -D FOREGROUND