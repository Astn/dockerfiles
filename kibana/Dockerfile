# Kibana 4.0.0-BETA2
# docker pull aharris/kibana
FROM barnybug/openjdk-7-jre
MAINTAINER Austin Harris <austin.w.harris+docker@gmail.com>

ENV KB_VERSION 4.0.0-BETA2

# install wget
RUN apt-get install -y wget && apt-get clean

# download and unpack kibana
RUN wget -q https://download.elasticsearch.org/kibana/kibana/kibana-$KB_VERSION.tar.gz -O - | tar zxvf - && \
    mv /kibana-$KB_VERSION /kibana

# use -v hostpath/kibana.yml:/kibana/config/kibana.yml to overwrite config 

VOLUME ["/kibana/data", "kibana/logs"]

EXPOSE 5601
CMD ["kibana/bin/kibana"]