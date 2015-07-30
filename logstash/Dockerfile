FROM logstash:latest

RUN plugin install logstash-output-elasticsearch-shield

COPY config/logstash.conf /etc/logstash/conf.d/logstash.conf

CMD ["logstash", "-f", "/etc/logstash/conf.d/logstash.conf"]
