#
# JEKYLL DOCKER IMAGE
#

FROM ruby:2.5.0

RUN apt-get -qq update \
    && apt-get -qq -y install locales \
        wget unzip \

# clean up

RUN apt clean
    && rm -rf /var/lib/apt/lists/*

# Set the locale

ENV LANG=de_DE.UTF-8
ENV LANGUAGE=de_DE:en
ENV LC_CTYPE=de_DE.UTF-8
ENV LC_ALL=de_DE.UTF-8
RUN locale-gen

# Install jekyll with bundler
ADD Gemfile .
RUN bundle install


RUN mkdir -p /srv/jekyll
WORKDIR /srv/jekyll