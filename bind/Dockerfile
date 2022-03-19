FROM ubuntu:focal

RUN apt-get update
RUN apt-get install bind9 bind9utils bind9-doc -y
COPY files/* /etc/bind/

# Enable IPv4
RUN #sed -i 's/OPTIONS=.*/OPTIONS="-4 -u bind"/' /etc/default/bind9

EXPOSE 53/udp 53/tcp 953/tcp

CMD ["/usr/sbin/named", "-g", "-c", "/etc/bind/named.conf", "-u", "bind"]