FROM ubuntu:14.04

MAINTAINER Alexander Tipugin <atipugin@gmail.com>

RUN apt-get update
RUN apt-get -y upgrade
RUN apt-get -y install wget build-essential

WORKDIR /tmp
RUN wget -O ruby-install-0.5.0.tar.gz https://github.com/postmodern/ruby-install/archive/v0.5.0.tar.gz &&\
  tar -xzvf ruby-install-0.5.0.tar.gz &&\
  cd ruby-install-0.5.0/ &&\
  make install

RUN ruby-install ruby 2.2.2
ENV PATH /opt/rubies/ruby-2.2.2/bin:$PATH

RUN echo "gem: --no-document" > ~/.gemrc
RUN gem install bundler pry
