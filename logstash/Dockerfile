ARG ELK_VERSION

# https://www.docker.elastic.co/
FROM docker.elastic.co/logstash/logstash:${ELK_VERSION}

RUN logstash-plugin install --preserve logstash-input-http
RUN logstash-plugin install --preserve logstash-filter-geoip

COPY ./logstash_filebeats.conf /usr/share/logstash/config
COPY ./logstash_http.conf /usr/share/logstash/config
COPY ./logstash_logger.conf /usr/share/logstash/config

# Add your logstash plugins setup here
# Example: RUN logstash-plugin install logstash-filter-json
