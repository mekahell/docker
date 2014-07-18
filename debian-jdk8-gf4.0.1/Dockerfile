FROM mgregori/debian-jdk8
MAINTAINER Mickael GREGORI <mickael.gregori@sfr.com>

# install wget and unzip
RUN apt-get install -y unzip wget

# download and install glassfish 4
RUN wget -q --no-cookies --no-check-certificate "http://dlc.sun.com.edgesuite.net/glassfish/4.0.1/promoted/latest-glassfish.zip" -O /tmp/glassfish-4.0.1.zip
RUN unzip /tmp/glassfish-4.0.1.zip -d /opt

# remove the downloaded zip
RUN rm /tmp/glassfish-4.0.1.zip

RUN echo 'export GF_HOME="/opt/glassfish4"' >> ~/.bashrc
ENV GF_HOME /opt/glassfish4

ENV PATH $PATH:$GF_HOME/bin
RUN export PATH=$PATH

EXPOSE 8080 4848

CMD asadmin start-domain --verbose