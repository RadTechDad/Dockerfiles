FROM ubuntu

RUN apt-get update && apt-get upgrade

RUN apt install -y bind9 bind9utils bind9-doc dnsutils

ENTRYPOINT ["named", "-g", "-c", "/etc/bind/named.conf", "-u", "bind"]