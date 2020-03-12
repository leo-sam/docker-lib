FROM ubuntu:18.04
MAINTAINER Andreas Lang <andreas.lang@aquilainsight.com>
ENV TERM=xterm \
    MIRROR=https://www.apache.org/dist/
ENV ZEPPELIN_VERSION=0.8.2 \ 
    ZEPPELIN_SRV_DIR=/srv/zeppelin
ENV ZEPPELIN_ARCHIVE=zeppelin-$ZEPPELIN_VERSION-incubating-bin-all
ENV ZEPPELIN_HOME=/opt/zeppelin/$ZEPPELIN_ARCHIVE \
    ZEPPELIN_NOTEBOOK_DIR=$ZEPPELIN_SRV_DIR/notebooks

RUN apt-get update && apt-get install -y curl openjdk-8-jdk python-numpy

RUN mkdir /opt/zeppelin
WORKDIR /opt/zeppelin

RUN curl $MIRROR/zeppelin/zeppelin-${ZEPPELIN_VERSION}/zeppelin-${ZEPPELIN_VERSION}-bin-all.tgz | tar xfz -
COPY lib/*.jar ${ZEPPELIN_HOME}/lib/
EXPOSE 8080 ENV PATH=$PATH:$ZEPPELIN_HOME/bin RUN mkdir -p $ZEPPELIN_NOTEBOOK_DIR
WORKDIR $ZEPPELIN_SRV_DIR
ADD run.sh run.sh
CMD $ZEPPELIN_SRV_DIR/run.sh
