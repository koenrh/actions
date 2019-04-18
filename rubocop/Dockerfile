FROM ruby:2.6.3-alpine3.8@sha256:4697814fcda30623bea086f803f12d79c107990f8a083e6d9ff3d7276fa3d037

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
