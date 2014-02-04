# basic jetty docker build file
FROM dockerfile/java

MAINTAINER Michael Dodsworth michael@dodsy.me

# fetch and untar Jetty
ADD http://eclipse.org/downloads/download.php?file=/jetty/8.1.14.v20131031/dist/jetty-distribution-8.1.14.v20131031.tar.gz&r=1 /opt
RUN mv /opt/jetty-* /opt/jetty

# create a jetty user
RUN useradd jetty -U -s /bin/false
RUN chown -R jetty:jetty /opt/jetty

USER jetty
WORKDIR /opt/jetty
EXPOSE 8080

CMD ["java", "-Djetty.home=/opt/jetty", "-jar", "start.jar"]
