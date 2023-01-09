FROM pihole/pihole:latest

RUN RUN apt-get update && apt-get install -y unbound

COPY pi-hole.conf /etc/unbound/unbound.conf.d/pi-hole.conf

ENTRYPOINT ./s6-init