FROM balenalib/raspberry-pi-node:10
RUN apt-get update \
&& apt-get install ca-certificates wget 
RUN wget https://artifacts.elastic.co/downloads/kibana/kibana-7.9.1-amd64.deb \
&& dpkg -i --force-all kibana-7.9.1-amd64.deb \
&& rm kibana-7.9.1-amd64.deb 
RUN ln -sf /usr/local/bin/node /usr/share/kibana/node/bin/node \
    && ln -sf /usr/local/bin/npm /usr/share/kibana/node/bin/npm
RUN chown -R kibana /usr/share/kibana
USER kibana
RUN mkdir /usr/share/kibana/config
COPY  kibana.yml /usr/share/kibana/config/kibana.yml
EXPOSE 5601
CMD  ["/usr/share/kibana/bin/kibana"]
