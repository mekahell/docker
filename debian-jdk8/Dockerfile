FROM debian:latest
MAINTAINER Mickael GREGORI <mickael.gregori@sfr.com>

# update sources.list to retrieve the JDK with apt
RUN echo "deb http://ppa.launchpad.net/webupd8team/java/ubuntu trusty main" | tee /etc/apt/sources.list.d/webupd8team-java.list
RUN echo "deb-src http://ppa.launchpad.net/webupd8team/java/ubuntu trusty main" | tee -a /etc/apt/sources.list.d/webupd8team-java.list
RUN apt-key adv --keyserver keyserver.ubuntu.com --recv-keys EEA14886

# update and upgrade
RUN apt-get -y update
RUN apt-get -y upgrade
RUN apt-get -y dist-upgrade

# install perl for debconf
RUN apt-get install -y perl

# install JDK8
RUN echo oracle-java8-installer shared/accepted-oracle-license-v1-1 select true | /usr/bin/debconf-set-selections
RUN apt-get install -y oracle-java8-installer oracle-java8-set-default maven
