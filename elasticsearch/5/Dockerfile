FROM openjdk:8-jdk
MAINTAINER Surittec <surittec.com.br>


ENV ELASTICSEARCH_VERSION=5.5.3

RUN \
    curl -L https://artifacts.elastic.co/downloads/elasticsearch/elasticsearch-$ELASTICSEARCH_VERSION.tar.gz -o elasticsearch-$ELASTICSEARCH_VERSION.tar.gz && \
    tar -xzf elasticsearch-$ELASTICSEARCH_VERSION.tar.gz && \
    mv elasticsearch-$ELASTICSEARCH_VERSION /opt/elasticsearch && \
    rm elasticsearch-$ELASTICSEARCH_VERSION.tar.gz

RUN \
   echo 'network.host: 0.0.0.0' >> /opt/elasticsearch/config/elasticsearch.yml

RUN \
    useradd -r elasticsearch && \
    chown -R elasticsearch:elasticsearch /opt/elasticsearch

USER elasticsearch

ENTRYPOINT ["/opt/elasticsearch/bin/elasticsearch"]

EXPOSE 9200 9300

