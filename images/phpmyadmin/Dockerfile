FROM phpmyadmin/phpmyadmin:latest

RUN chmod g+rwx -R /var /sessions /etc
RUN echo http://dl-2.alpinelinux.org/alpine/edge/community/ >> /etc/apk/repositories && \ 
    apk --no-cache add shadow 
RUN adduser -S -G nobody pma && usermod -a -G root pma

RUN sed -i 's/listen 80/listen 8080/g' /etc/nginx.conf && \
    sed -i 's#pid /nginx.pid;#pid /run/nginx.pid;#g' /etc/nginx.conf && \
    sed -i 's/user nobody;/# user nobody;/g' /etc/nginx.conf && \
    mkdir -p /var/lib/nginx/logs && touch /var/lib/nginx/logs/error.log
 
RUN mkdir -p /var/nginx/client_body_temp /var/run/php /var/lib/nginx/logs && \
    chown -R pma:nobody /sessions /var/nginx/client_body_temp /var/tmp/nginx /var/run/php /var/log /run /var/lib/nginx
RUN sed -i 's/user=/; user=/g' /etc/supervisor.d/nginx.ini &&  sed -i 's/user=/; user=/g' /etc/supervisor.d/php.ini

EXPOSE 8080
USER pma
