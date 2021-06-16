FROM node:16.3.0-alpine@sha256:8fdfe93e621116e8a7b663dd6d9e1dc0dbc952d6de9b87ad3218d83ba67bfb92

LABEL name="ESLint"
LABEL maintainer="Koen Rouwhorst <info@koenrouwhorst.nl>"

LABEL "com.github.actions.name"="GitHub Action for ESLint"
LABEL "com.github.actions.icon"="code"
LABEL "com.github.actions.color"="blue"

ENV ESLINT_VERSION=6.8.0 \
    ESLINT_CHECKSUM="10da0d30a69d0ac0b6ea690fdd1e5dd8edf61b5a5f1433d99f976452067947b8" \
    PATH=/usr/lib/node_modules/.bin:$PATH

RUN set -x && \
    wget -O "eslint-$ESLINT_VERSION.tgz" "https://registry.npmjs.org/eslint/-/eslint-$ESLINT_VERSION.tgz" && \
    echo "${ESLINT_CHECKSUM} *eslint-$ESLINT_VERSION.tgz" | sha256sum -c - && \
    npm install -g "eslint-$ESLINT_VERSION.tgz" && \
    rm -rf "eslint-$ESLINT_VERSION.tgz" \
        /usr/share/man \
        /root/.npm /root/.node-gyp \
        /usr/lib/node_modules/npm/man \
        /usr/lib/node_modules/npm/doc \
        /usr/lib/node_modules/npm/html \
        /tmp/*

COPY entrypoint.sh /entrypoint.sh
ENTRYPOINT ["/entrypoint.sh"]
