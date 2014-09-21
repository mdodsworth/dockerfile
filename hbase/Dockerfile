FROM mdodsworth/java8

RUN \
  cd /tmp && \
  wget -q http://supergsego.com/apache/hbase/stable/hbase-0.98.6.1-hadoop2-bin.tar.gz && \
  tar xfz hbase-0.98.6.1-hadoop2-bin.tar.gz && \
  rm -f hbase-0.98.6.1-hadoop2-bin.tar.gz && \
  mv hbase-0.98.6.1-hadoop2 /hbase

ADD hbase-site.xml /hbase/conf/hbase-site.xml

VOLUME ["/data"]

# zookeeper
EXPOSE 2181
# HBase Master API port
EXPOSE 60000
# HBase Master Web UI
EXPOSE 60010
# Regionserver API port
EXPOSE 60020
# HBase Regionserver web UI
EXPOSE 60030

CMD ["/hbase/bin/hbase", "master", "start"]
