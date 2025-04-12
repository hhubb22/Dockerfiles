FROM debian:unstable-slim

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update && \
    apt-get install -y --no-install-recommends \
    build-essential \
    devscripts \
    debhelper \
    lintian \
    sudo \
    equivs \
    adduser \
    git \
    wget \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

RUN useradd --create-home --uid 1000 --shell /bin/bash builder && \
    adduser builder sudo && \
    echo "builder ALL=(ALL) NOPASSWD: ALL" > /etc/sudoers.d/builder && \
    chmod 0440 /etc/sudoers.d/builder

USER builder

WORKDIR /home/builder/src

CMD ["/bin/bash"]