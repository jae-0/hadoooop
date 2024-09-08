FROM ubuntu:18.04

WORKDIR /root

# install openssh-server, openjdk and wget
RUN apt-get update && apt-get install -y openssh-server openssh-client openjdk-8-jdk wget

# set environment variable
ENV JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64 

# ssh without key
RUN ssh-keygen -t rsa -f ~/.ssh/id_rsa -P '' && \
    cat ~/.ssh/id_rsa.pub >> ~/.ssh/authorized_keys

CMD cd /home/openec/openec-v1.0.0/hdfs3-integration && \
    ./install.sh

CMD [ "sh", "-c", "service ssh start; bash"]
