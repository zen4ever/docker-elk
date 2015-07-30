FROM elasticsearch:latest

ENV ES_JAVA_OPTS="-Des.path.conf=/etc/elasticsearch"

RUN plugin -i elasticsearch/marvel/latest
RUN plugin -i elasticsearch/license/latest
RUN plugin -i elasticsearch/shield/latest

RUN /usr/share/elasticsearch/bin/shield/esusers useradd marvel_export -p 'marvel' -r marvel_agent
RUN /usr/share/elasticsearch/bin/shield/esusers useradd logstash -p 'logstash' -r logstash,transport_client
RUN /usr/share/elasticsearch/bin/shield/esusers useradd kibana -p 'kibana' -r kibana4_server
RUN /usr/share/elasticsearch/bin/shield/esusers useradd marvel_admin -p 'marvel' -r marvel_user
RUN /usr/share/elasticsearch/bin/shield/esusers useradd kibana_admin -p 'kibana' -r kibana4

COPY config/elasticsearch.yml /etc/elasticsearch/elasticsearch.yml
