FROM bitnami/minideb:jessie
MAINTAINER Nicolás Pace <nico@libre.ws>

RUN install_packages curl

RUN curl http://deb.kamailio.org/kamailiodebkey.gpg | apt-key add - && \
    echo "deb http://deb.kamailio.org/kamailio jessie main" > /etc/apt/sources.list.d/kamailio.list && \
    echo "deb-src http://deb.kamailio.org/kamailio jessie main" >> /etc/apt/sources.list.d/kamailio.list && \
    install_packages kamailio kamailio-mysql-modules kamailio-websocket-modules kamailio-tls-modules kamailio-presence-modules kamailio-sctp-modules kamailio-outbound-modules kamailio-extra-modules

COPY ./overlay/etc/kamailio/kamailio.cfg /etc/kamailio/

EXPOSE 5090
EXPOSE 10080
EXPOSE 10443

ENTRYPOINT /usr/sbin/kamailio -m 64 -M 8 -DD
