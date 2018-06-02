FROM phpmyadmin/phpmyadmin:latest

RUN chmod g+rwx -R /var /sessions /etc
RUN echo http://dl-2.alpinelinux.org/alpine/edge/community/ >> /etc/apk/repositories && \ 
    apk --no-cache add shadow 
RUN adduser -S -G nobody pma && usermod -a -G root pma 
RUN mkdir -p /var/nginx/client_body_temp /var/run/php && \
    chown -R pma:nobody /sessions /var/nginx/client_body_temp /var/run/php /var/log
RUN sed -i 's/user=/; user=/g' /etc/supervisor.d/nginx.ini &&  sed -i 's/user=/; user=/g' /etc/supervisor.d/php.ini

