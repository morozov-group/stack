# Magento 2 Stack for Kubernetes/Openshift

This replository contains everything need to deploy Magento 2 Stack with best possible performance.
Set of docker images and configurations to deploy Magento 2 demo project in Openshift.

## For Openshift

**HTTP/2 offload** is none by NGINX [Origin router](https://github.com/openshift/origin/tree/master/images/router/nginx)

**ACME SSL certicate automations** are done via  [openshift-acme](https://github.com/tnozicka/openshift-acme/tree/master/deploy/letsencrypt-live/cluster-wide)

## For GKE

TBD

## Regular stack
Varnish - 6.0.0 Image config [Source for Image](https://github.com/morozov-group/stack/tree/master/images/varnish)

PHP from Magento 2 - Source to image for Magento is based on following patched verion of image. [Source for Image](https://github.com/morozov-group/s2i-php-container/tree/master/7.1)

Redis - docker hub.

MySQL/Percona - docker hub.

PHPMyAdmin - here source to Image configuration.[Source2image](https://github.com/morozov-group/stack/tree/master/images/phpmyadmin/.s2i/bin)

Elasticsearch 5.x compatible with Elastic Suite.[Source for Image](https://github.com/morozov-group/stack/tree/master/images/elasticsearch)
