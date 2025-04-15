FROM ubuntu:latest

WORKDIR /app

RUN apt-get update

RUN apt-get install -y --no-install-recommends \
    build-essential \
    g++ \
    cmake \
    make \
    git \
    wget \
    curl \
    zip \
    unzip

RUN apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*


VOLUME /app

CMD ["bash"]