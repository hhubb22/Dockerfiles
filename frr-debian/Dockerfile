FROM debian:unstable

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update \
 && apt-get install -y --no-install-recommends \
    # FRR 路由套件
    frr \
    frr-pythontools \
    # 网络诊断工具
    iproute2 \
    iputils-ping \
    net-tools \
    traceroute \
    curl \
    wget \
    # 经典编辑器
    nano \
    # 系统监控与进程管理
    procps \
    htop \
    # 现代文件搜索与查看
    ripgrep \
    fd-find \
    bat \
    silversearcher-ag \
    # 交互式命令行增强
    fzf \
 && rm -rf /var/lib/apt/lists/*


CMD ["bash", "-c", "chown frr:frr /etc/frr/*.conf && /usr/lib/frr/frrinit.sh start && tail -f /dev/null"]
