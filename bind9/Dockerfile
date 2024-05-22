#Base Bind9 Image
FROM ubuntu

#Update and upgrade installed system pacakges
RUN apt-get update && apt-get upgrade

#Install required tools and dependencies
RUN apt install -y \
        bind9utils \
        bind9-doc \ 
        dnsutils \ 
        geoip-bin \
        net-tools

# Expose Ports
EXPOSE 53/tcp
EXPOSE 53/udp

LABEL maintainer="Darrell Dudics <darrell@radtechdad.com>" \
      version="1.0"

# Start the Name Service
CMD ["/usr/sbin/named", "-g", "-c", "/etc/bind/named.conf", "-u", "bind"]