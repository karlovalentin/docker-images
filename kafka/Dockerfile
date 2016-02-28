FROM klustera/java8

# Basado en Kafka Docker de Wurstmeister
MAINTAINER Adolfo De Unánue <adolfo@klustera.com>

ENV KAFKA_VERSION="0.9.0.0"
ENV SCALA_VERSION="2.11"

ENV KAFKA_HOME /opt/kafka_${SCALA_VERSION}-${KAFKA_VERSION}

ADD ./scripts/download.sh /tmp/download.sh

RUN \
    /tmp/download.sh \
    && tar xfz /tmp/kafka_${SCALA_VERSION}-${KAFKA_VERSION}.tgz -C /opt \
    && rm /tmp/kafka_${SCALA_VERSION}-${KAFKA_VERSION}.tgz

ADD ./scripts/start-kafka.sh /usr/bin/start-kafka.sh
ADD ./scripts/broker-list.sh /usr/bin/broker-list.sh
ADD ./scripts/create-topics.sh /usr/bin/create-topics.shed

CMD ["start-kafka.sh"]
