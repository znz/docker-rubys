FROM ubuntu:12.04
MAINTAINER Kazuhiro NISHIYAMA <zn@mbf.nifty.com>

# build depends
RUN apt-get install -y git-core wget build-essential autoconf libssl-dev libyaml-dev libreadline6 libreadline6-dev zlib1g zlib1g-dev subversion bison
# utils
RUN apt-get install -y bash-completion vim
# rbenv and ruby-build
RUN git clone https://github.com/sstephenson/rbenv /opt/rbenv
RUN git clone https://github.com/sstephenson/ruby-build /opt/rbenv/plugins/ruby-build
ADD rbenv.sh /etc/profile.d/rbenv.sh

# install rubys
RUN bash -c 'set -euo pipefail; \
 . /etc/profile.d/rbenv.sh; \
 git clone https://github.com/znz/rbenv-plug /opt/rbenv/plugins/rbenv-plug; \
 rbenv plug each; \
 export CONFIGURE_OPTS="--disable-install-rdoc --disable-install-doc"; \
 for v in \
 1.8.7-p375 \
 1.9.3-p484 \
 2.0.0-p353 \
 2.1.0 \
 ; do \
 echo install $v; \
 rbenv install $v; \
 done \
 '

CMD ["/bin/bash", "-l"]
