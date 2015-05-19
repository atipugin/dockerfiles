FROM atipugin/ruby:2.2.2

MAINTAINER Alexander Tipugin <atipugin@gmail.com>

RUN apt-get -y install nodejs

RUN echo "deb http://apt.postgresql.org/pub/repos/apt/ trusty-pgdg main" > /etc/apt/sources.list.d/pgdg.list
RUN wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc | apt-key add -
RUN apt-get update
RUN apt-get -y install libpq-dev

ENV APP_ROOT /rails
ENV RAILS_ENV production

WORKDIR $APP_ROOT
ONBUILD ADD Gemfile $APP_ROOT/Gemfile
ONBUILD ADD Gemfile.lock $APP_ROOT/Gemfile.lock
ONBUILD RUN bundle install
ONBUILD ADD . $APP_ROOT
