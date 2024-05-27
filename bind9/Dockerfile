#Base Bind9 Image
FROM ubuntu

USER root

#Update and upgrade installed system pacakges
RUN apt-get update && apt-get -y upgrade

#Install required tools and dependencies
RUN apt install -y \
        bind9 \
        bind9utils \
        bind9-doc \ 
        dnsutils \ 
        geoip-bin \
        net-tools

RUN mkdir -p /run/named \
        && chown bind:bind /run/named

# Expose Ports
EXPOSE 53/tcp
EXPOSE 53/udp

LABEL maintainer="Darrell Dudics <darrell@radtechdad.com>" \
      version="1.0"

USER bind

# Start the Name Service
CMD ["/usr/sbin/named", "-g", "-c", "/etc/bind/named.conf", "-u", "bind"]