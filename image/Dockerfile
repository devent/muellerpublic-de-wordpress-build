FROM  robobeerun/wordpress:v4.9.8-php5.6-fpm-r1
LABEL maintainer "Erwin Mueller <erwin.mueller@deventm.com>"

USER root

RUN set -x \
  && /install_wp_theme.sh https://downloads.wordpress.org/theme/carton.1.0.7.zip '59ebcb16edc5a3bba52cbde5ac8c93288c259a48637445910f081a8add88b666'

# Finishing up.

USER ${WEB_USER}

WORKDIR ${WEB_ROOT}

ENTRYPOINT ["/docker-entrypoint.sh"]

CMD ["php-fpm"]
