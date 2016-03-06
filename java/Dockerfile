FROM ubuntu

COPY ./upload/* /opt/

RUN sed -i 's/archive.ubuntu.com/mirrors.yun-idc.com/g' /etc/apt/sources.list && \
  cd /opt/ && \
  mv /opt/locale /etc/default/locale && \
  apt-get update && \
  apt-get upgrade -y && \
  ls

RUN apt-get install wget -y

RUN apt-get install -y --force-yes python-software-properties software-properties-common 

RUN sudo -E add-apt-repository ppa:openjdk-r/ppa -y

RUN apt-get install -y --force-yes unzip curl git docker.io jq ssh

RUN mkdir -p /var/run/sshd

ENV TZ="Asia/Shanghai"

RUN cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime && \
  echo "zh_CN.UTF-8 UTF-8" > /var/lib/locales/supported.d/local && \
  echo "en_US.UTF-8 UTF-8" >> /var/lib/locales/supported.d/local && \
#  echo "zh_CN.UTF-8 UTF-8" >> /var/lib/locales/supported.d/local && \
  locale-gen
  
RUN apt-get update && apt-get install openjdk-8-jdk -y

RUN apt-get install -y --force-yes maven

RUN echo "en_GB.UTF-8 UTF-8" >> /var/lib/locales/supported.d/local && \
  locale-gen

ENV LANG=en_GB.UTF-8
ENV LANGUAGE=en_GB:en
