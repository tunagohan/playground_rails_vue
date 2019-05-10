FROM ruby:2.6.3-stretch
LABEL maintainer="k-waragai <kazuxtuna@gmail.com>"

RUN rm /bin/sh && ln -s /bin/bash /bin/sh

RUN apt-get update -qq

RUN apt-get install -y build-essential libpq-dev

RUN curl -sL https://deb.nodesource.com/setup_10.x | bash - && \
    apt-get install -y nodejs

RUN curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | apt-key add - && \
    echo "deb https://dl.yarnpkg.com/debian/ stable main" | tee /etc/apt/sources.list.d/yarn.list && \
    apt-get update && apt-get install -y yarn

RUN mkdir -p /app
WORKDIR /app

RUN gem install bundler

ADD Gemfile Gemfile
ADD Gemfile.lock Gemfile.lock

RUN bundle install

ADD . /myapp