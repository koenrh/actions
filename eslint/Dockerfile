FROM node:11.9-alpine@sha256:9ed863b96874cdebd92a772d946ae7ca0dfeaf0a1308ad9a382efce8eae8608c

LABEL name="ESLint"
LABEL maintainer="Koen Rouwhorst <info@koenrouwhorst.nl>"

LABEL "com.github.actions.name"="GitHub Action for ESLint"
LABEL "com.github.actions.icon"="code"
LABEL "com.github.actions.color"="blue"

ENV ESLINT_VERSION=5.11.1 \
    PATH=/usr/lib/node_modules/.bin:$PATH

RUN npm install -g eslint@${ESLINT_VERSION} && \
    rm -rf /usr/share/man /tmp/* \
           /root/.npm /root/.node-gyp \
           /usr/lib/node_modules/npm/man \
           /usr/lib/node_modules/npm/doc \
           /usr/lib/node_modules/npm/html

COPY entrypoint.sh /entrypoint.sh
ENTRYPOINT ["/entrypoint.sh"]
