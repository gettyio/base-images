FROM frolvlad/alpine-java:jdk8-full as build

USER root

# installs dependencies packages
RUN apk update \
&& apk -U upgrade \
    && apk add --no-cache --update bash curl wget \
        tar tzdata iputils unzip findutils git gettext gdb lsof patch \
        libcurl libxml2 libxslt openssl-dev zlib-dev \
        make automake gcc g++ binutils-gold linux-headers paxctl libgcc libstdc++ \
        python gnupg ncurses-libs \
    && rm -rf /var/cache/apk/*

# installs gradle 4.3
RUN curl -LO https://downloads.gradle.org/distributions/gradle-4.3-bin.zip \
    && mkdir /opt/gradle \
    && unzip -d /opt/gradle gradle-4.3-bin.zip \
    && mv /opt/gradle/gradle-4.3/* /opt/gradle/ \
    && rm -rf /opt/gradle/gradle-4.3/
    #&& chmod +x /usr/local/bin/gradle

ENV PATH=$PATH:/opt/gradle/bin