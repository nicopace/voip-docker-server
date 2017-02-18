FROM bitnami/minideb:jessie
MAINTAINER Nicolás Pace <nico@libre.ws>

RUN install_packages rtpproxy

EXPOSE 9082
EXPOSE 16384-16639/UDP
ENTRYPOINT /usr/bin/rtpproxy -F -f
