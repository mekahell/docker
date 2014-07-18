# Debian &amp; Oracle JDK8

### How to build

```
$ git clone https://github.com/mekahell/docker.git
$ cd debian-jdk8-gf4.0.1
$ docker build .
```
### How to run

Don't forget to define the ports to expose :
* 8080 for webapps
* 4848 for admin

You can precise more if you need.

```
$ docker run -p 8080 -p 4848 --name="glassfish" -d -t debian-jdk8-gf4.0.1 asadmin start-domain && tail -f /opt/glassfish4/glassfish/domains/domain1/logs/server.log
```

Enjoy