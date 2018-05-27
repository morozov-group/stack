FROM centos:7

RUN yum -y update && \ 
  yum -y install wget && \
  wget https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm && \
  wget http://rpms.remirepo.net/enterprise/remi-release-7.rpm && \
  rpm -Uvh remi-release-7.rpm epel-release-latest-7.noarch.rpm && \
  yum-config-manager --enable remi-php71

RUN yum -y install ssmtp cronie

RUN yum -y install php-fpm php-cli \
  php-bcmath \
  php-dom \
  php-gd \
  php-intl \
  php-mbstring \
  php-mcrypt \
  php-pecl-ssh2 \
  php-pecl-memcache \
  php-pecl-memcached \
  php-mysqlnd \
  php-pecl-redis4 \
  php-pecl-imagick \ 
  php-soap \
  php-zip \
  php-opcache && \
  mkdir -p /run/php-fpm && \
  echo "Installed All"

RUN ln -sf /dev/stderr /var/log/php-fpm/www-error.log && \
  ln -sf /dev/stderr /var/log/php-fpm/www-slow.log

RUN yum -y install php-pecl-xdebug && \
  mv /etc/php.d/15-xdebug.ini /etc/php.d/15-xdebug.ini.dev 


