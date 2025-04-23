FROM debian:unstable

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update \
 && apt-get install -y --no-install-recommends \
    frr \
    frr-pythontools \
    iproute2 \
    iputils-ping \
    net-tools \
    traceroute \
    curl \
    wget \
    nano \
 && rm -rf /var/lib/apt/lists/*

CMD ["bash", "-c", "chown frr:frr /etc/frr/*.conf && /usr/lib/frr/frrinit.sh start && tail -f /dev/null"]
