FROM debian
WORKDIR /hugo
RUN sed -i s@/deb.debian.org/@/mirrors.aliyun.com/@g /etc/apt/sources.list \
    && apt-get clean \
    && apt-get update \
    && apt-get -y install wget git \
    && wget -O hugo.deb https://style.oribos.city/app/hugo_extended_0.83.1_Linux-64bit.deb \
    && dpkg -i hugo.deb