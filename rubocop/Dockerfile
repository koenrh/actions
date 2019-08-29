FROM ruby:2.6.3-alpine3.8@sha256:70227bd490856f24614a636f5c7bacdd58167477f042593822dd49e33097c602

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
