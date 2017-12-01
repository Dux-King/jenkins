FROM jenkins:alpine
ENV TIME_ZONE Asia/Shanghai
USER root
RUN apk add --no-cache tzdata tar wget && \
    echo "${TIME_ZONE}" > /etc/timezone && \
    ln -sf /usr/share/zoneinfo/${TIME_ZONE} /etc/localtime && \
    mkdir /tmp1 && \
    cd /tmp1 && \
    wget https://download.docker.com/linux/static/stable/x86_64/docker-17.09.0-ce.tgz && \
    tar -zxvf docker-17.09.0-ce.tgz && \
    cp docker/docker* /bin/ && \
    wget http://mirrors.shuosc.org/apache/maven/maven-3/3.3.9/binaries/apache-maven-3.3.9-bin.tar.gz && \
    tar -zxvf apache-maven-3.3.9-bin.tar.gz && \
    mv apache-maven-3.3.9 /usr/local/maven && \
    cd / && \
    rm -rf /tmp1
USER jenkins
