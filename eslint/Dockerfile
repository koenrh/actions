FROM node:12.8-alpine@sha256:ee0ad356063b2e16458109cf009715dda84664b26481415cb009ee2b79b79441

LABEL name="ESLint"
LABEL maintainer="Koen Rouwhorst <info@koenrouwhorst.nl>"

LABEL "com.github.actions.name"="GitHub Action for ESLint"
LABEL "com.github.actions.icon"="code"
LABEL "com.github.actions.color"="blue"

ENV ESLINT_VERSION=5.12.1 \
    ESLINT_CHECKSUM="642ba59e25de166cf730d6eeb0af9b6f37ab21a04f5726baae6b1588da4afa60" \
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
