FROM balenalib/raspberry-pi-openjdk:8-stretch
RUN apt-get update \
&& apt-get install -y ca-certificates wget \
&& rm -rf /var/lib/apt/lists/*
RUN wget https://artifacts.elastic.co/downloads/elasticsearch/elasticsearch-7.9.1-arm64.deb \
&& dpkg -i --force-all elasticsearch-7.9.1-arm64.deb \
&& rm elasticsearch-7.9.1-arm64.deb
USER elasticsearch 
COPY elasticsearch.yml /etc/elasticsearch/elasticsearch.yml
EXPOSE 9200 9300
CMD  /usr/share/elasticsearch/bin/elasticsearch
