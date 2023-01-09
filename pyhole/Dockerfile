FROM pihole/pihole:latest

RUN apt-get update && apt-get install -y unbound

# BASED ON https://github.com/chriscrowe/docker-pihole-unbound/tree/main/one-container
COPY lighttpd-external.conf /etc/lighttpd/external.conf 
COPY pi-hole.conf /etc/unbound/unbound.conf.d/pi-hole.conf
COPY 99-edns.conf /etc/dnsmasq.d/99-edns.conf
RUN mkdir -p /etc/services.d/unbound
COPY unbound-run /etc/services.d/unbound/run
RUN chmod +x /etc/services.d/unbound/run

ENTRYPOINT ./s6-init