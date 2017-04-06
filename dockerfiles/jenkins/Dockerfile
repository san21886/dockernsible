FROM jenkins:2.46.1.extra

USER root

RUN apt-get update && apt-get install -y zlib1g-dev build-essential libssl-dev libreadline-dev libyaml-dev libsqlite3-dev sqlite3 libxml2-dev libxslt1-dev libcurl4-openssl-dev python-software-properties libffi-dev libgdbm-dev libncurses5-dev automake libtool bison libffi-dev gawk libgmp-dev pkg-config libgmp-dev

USER jenkins

RUN curl -sSL https://get.rvm.io | bash -s stable && /bin/bash -c 'source ~/.rvm/scripts/rvm && rvm autolibs fail && rvm install 2.4.0 && rvm use 2.4.0 && gem install sass'
#RUN /bin/bash -c 'source ~/.rvm/scripts/rvm && rvm install 2.1 && rvm use 2.1 && gem install sass'
