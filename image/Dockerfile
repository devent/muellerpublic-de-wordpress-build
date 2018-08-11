FROM  robobeerun/wordpress:v4.9.7-php5.6-fpm-r3
LABEL maintainer "Erwin Mueller <erwin.mueller@deventm.com>"

USER root

RUN set -x \
  && /install_wp_plugin.sh https://downloads.wordpress.org/plugin/miniorange-login-with-eve-online-google-facebook.zip '45814c1f1e7cb6ffcd2516482cf92b7ef3be8e5c3b1eb80e69751b74f95d2e39'

RUN set -x \
  && /install_wp_theme.sh https://downloads.wordpress.org/theme/carton.1.0.7.zip '59ebcb16edc5a3bba52cbde5ac8c93288c259a48637445910f081a8add88b666'

# Finishing up.

USER ${WEB_USER}

WORKDIR ${WEB_ROOT}

ENTRYPOINT ["/docker-entrypoint.sh"]

CMD ["php-fpm"]
