# Magento 2 Stack for Kubernetes/Openshift

This replository contains refrences to everything need to deploy Magento 2 Stack with best possible performance.
Set of docker images and configurations to deploy Magento 2 demo project in Openshift.

## For Openshift

**SSL offload with HTTP/2** is done by NGINX [Origin router](https://github.com/openshift/origin/tree/master/images/router/nginx)

**ACME SSL certificate automations** are done via  [openshift-acme](https://github.com/tnozicka/openshift-acme/tree/master/deploy/letsencrypt-live/cluster-wide)

## For GKE

**SSL offload with HTTP/2** is done by regular ingress.

**ACME SSL certificate automations** are done via [cert-manager](https://cert-manager.readthedocs.io/en/latest/getting-started/2-installing.html)

## Regular stack

**Varnish** - 6.0.0 Image config [Source for Image](https://github.com/morozov-group/stack/tree/master/images/varnish)

**PHP 7.1 from Magento 2** - Source to image for Magento is based on following patched verion of image. [Source for Image](https://github.com/morozov-group/s2i-php-container/tree/master/7.1)

**Redis** - session storage and cache storage from docker hub.

**MySQL/Percona** - master database from docker hub.


## Usefull Extras 

**Elasticsearch 5.x** compatible with Elastic Suite. [Source for Image](https://github.com/morozov-group/stack/tree/master/images/elasticsearch)
Includes required modules + russian language analyzer.

**PHPMyAdmin** - here source to Image configuration. [Source2image](https://github.com/morozov-group/stack/tree/master/images/phpmyadmin/.s2i/bin)
