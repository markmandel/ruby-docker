FROM google/debian:wheezy

RUN apt-get update && \
    apt-get install -qy --no-install-recommends \
        autoconf \
        build-essential \
        ca-certificates \
        curl \
        git \
        libffi-dev \
        libgdbm-dev \
        libgmp-dev \
        libncurses5-dev \
        libqdbm-dev \
        libreadline6-dev \
        libssl-dev \
        libyaml-dev \
        libz-dev \
        systemtap && \
    apt-get clean
RUN mkdir -p /usr/src && \
    curl http://ftp.ruby-lang.org/pub/ruby/2.1/ruby-2.1.5.tar.bz2 | \
        tar -C /usr/src -xj
RUN cd /usr/src/ruby-2.1.5 && \
    autoconf && \
    ./configure --prefix=/usr --disable-install-doc && \
    make && make install && make clean
RUN gem install -q --no-rdoc --no-ri bundler --version 1.7.6
