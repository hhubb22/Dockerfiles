FROM debian:unstable

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update \
 && apt-get install -y --no-install-recommends \
    # 基础网络 & 路由
    iproute2 \
    iputils-ping \
    net-tools \
    traceroute \
    mtr \
    dnsutils \
    whois \
    # 性能测试
    iperf3 \
    speedtest-cli \
    # 安全扫描与连接
    nmap \
    netcat-openbsd \
    socat \
    openssh-client \
    telnet \
    # HTTP/HTTPS 客户端
    curl \
    wget \
    httpie \
    # 包捕获与协议分析
    tcpdump \
    tshark \
    # JSON/YAML 处理
    jq \
    yq \
    # FTP/SFTP 客户端
    lftp \
    # 带宽/流量监控
    iftop \
    bmon \
    # 系统监控
    htop \
    # 编辑器与版本管理
    vim \
    nano \
    git \
 && apt-get clean \
 && rm -rf /var/lib/apt/lists/*

CMD ["bash"]
