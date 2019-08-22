FROM node:12.9-alpine@sha256:b1a32805dbe3894722db93b7f1a3489a208ddf4e9b9341d1e8d3e366fcc0998d

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
