FROM alpine:3.7

LABEL maintainer="Jack Peng <invclan@foxmail.com>"


# docker build -t oracle-jre:1.0 .
# Don't copy
# COPY server-jre-8u171-linux-x64.tar.gz /usr/local

RUN apk --no-cache add ca-certificates wget \
    && wget -q -O /etc/apk/keys/sgerrand.rsa.pub https://raw.githubusercontent.com/sgerrand/alpine-pkg-glibc/master/sgerrand.rsa.pub \
    && wget https://github.com/sgerrand/alpine-pkg-glibc/releases/download/2.27-r0/glibc-2.27-r0.apk \
    && apk add glibc-2.27-r0.apk \
    && cd /usr/local \
    && wget https://github.com/cnjack-peng/ires/raw/master/server-jre-8u171-linux-x64.tar.gz \
    && tar -zvxf server-jre-8u171-linux-x64.tar.gz \
    && rm -rf server-jre-8u171-linux-x64.tar.gz 
    

ENV JAVA_HOME /usr/local/jdk1.8.0_171 
ENV CLASSPATH .:$JAVA_HOME/jre/lib/rt.jar:$JAVA_HOME/lib/dt.jar:$JAVA_HOME/lib/tools.jar
ENV PATH $PATH:$JAVA_HOME/bin:. 






