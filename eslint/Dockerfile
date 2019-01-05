FROM node:11.6-alpine@sha256:d2180576a96698b0c7f0b00474c48f67a494333d9ecb57c675700395aeeb2c35

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
