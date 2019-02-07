FROM fluent/fluentd:v1.3

RUN apk add --update \
        geoip \
        libmaxminddb \
    && apk add --update --virtual .build-deps \
        sudo \
        build-base \
        ruby-dev \
        geoip-dev \
        libmaxminddb-dev \
    && sudo gem install \
        fluent-plugin-rewrite-tag-filter \
        fluent-plugin-slack \
        fluent-plugin-elasticsearch \
        fluent-plugin-geoip \
        fluent-plugin-flowcounter \
    && sudo gem sources --clear-all \
    && apk del .build-deps \
    && rm -rf /var/cache/apk/* \
    /home/fluent/.gem/ruby/2.3.0/cache/*.gem
