# Dockerfile for dashing 
# http://shopify.github.io/dashing

FROM ubuntu:14.04
MAINTAINER Dieter Reuter <dieter.reuter@me.com>

ENV DEBIAN_FRONTEND noninteractive
RUN echo "deb http://archive.ubuntu.com/ubuntu/ trusty main universe" > /etc/apt/sources.list
RUN apt-get -yy update
RUN apt-get -yy upgrade


# install tools
RUN apt-get -yy install wget curl git-core

# install Dashing deps
RUN apt-get -yy install ruby ruby-dev gem
RUN apt-get -yy install bundler g++ make
RUN apt-get -yy install nodejs

# set default for gem/install to no-doc/no-ri
RUN echo "gem: --no-document --no-rdoc --no-ri" | tee ~/.gemrc

# install Dashing
RUN gem install dashing

# install our dashboard
RUN mkdir -p /opt/application
RUN git clone https://github.com/DieterReuter/dashboard-ntile.git /opt/application/dashboard-ntile
RUN cd /opt/application/dashboard-ntile; bundle install

# use Dashing webport 3030/tcp
EXPOSE 3030

# launch the dashboard
CMD ["/bin/sh", "-c", "cd /opt/application/dashboard-ntile && dashing start"]
