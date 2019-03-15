FROM ruby:2.6.2-alpine3.8@sha256:3cf51abdf621e9ec1b092deb5972d21102ea40dec53360ddf363894372db4a09

LABEL repository="https://github.com/koenrh/rubocop-action"
LABEL maintainer="Koen Rouwhorst <info@koenrouwhorst.nl>"

LABEL "com.github.actions.name"="RuboCop"
LABEL "com.github.actions.description"="RuboCop is a Ruby static code analyzer and code formatter."
LABEL "com.github.actions.icon"="flag"
LABEL "com.github.actions.color"="red"

RUN apk add --no-cache \
  build-base=~0.5

RUN addgroup -S rubocop && \
  adduser -S -g rubocop rubocop

RUN gem install rubocop --no-document

COPY entrypoint.sh /entrypoint.sh
ENTRYPOINT ["/entrypoint.sh"]
