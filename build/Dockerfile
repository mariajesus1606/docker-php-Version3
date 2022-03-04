FROM debian

EXPOSE 80

ADD bookmedik /var/www/html/
ADD script.sh /usr/local/bin/

RUN apt-get update && apt-get install -y apache2 \
libapache2-mod-php7.4 \
php7.4 \
php7.4-mysql \
&& apt-get clean \
&& rm -rf /var/lib/apt/lists/* \
&& chmod +x /usr/local/bin/script.sh

ENV DATABASE_USER bookmedik
ENV DATABASE_PASSWORD bookmedik
ENV DATABASE_HOST db

ENTRYPOINT ["script.sh"]
