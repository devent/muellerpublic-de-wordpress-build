FROM  robobeerun/wordpress:v5.2.0-php7.1-fpm-r.2
LABEL maintainer "Erwin Mueller <erwin.mueller@deventm.com>"

USER root

ADD rootfs/ /

RUN set -x \
  && chmod +x /*.sh

# Install plugins.

RUN set -x \
  && /install_all_wp_plugins.sh

# Install themes.

RUN set -x \
  && /install_all_wp_themes.sh

# Finishing up.

USER ${WEB_USER}

WORKDIR ${WEB_ROOT}

ENTRYPOINT ["/docker-entrypoint.sh"]

CMD ["php-fpm"]
