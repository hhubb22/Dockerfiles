# 使用官方最新的 openSUSE Tumbleweed 镜像作为基础
FROM opensuse/tumbleweed:latest

# 设置环境变量，确保 locale 和终端类型
ENV LANG=C.UTF-8
ENV TERM=xterm

# 更新软件源、安装所有必需和推荐的软件包、清理缓存和日志
# 所有操作合并到一条 RUN 指令中以最小化镜像层数
RUN zypper --non-interactive ref && \
    zypper --non-interactive install --no-recommends -y \
        # 核心系统与网络基础
        coreutils \
        bash \
        iproute2 \
        iputils \
        # 核心网络诊断工具
        traceroute \
        bind-utils \
        # 远程访问与数据传输
        openssh-clients \
        curl \
        wget \
        # 网络流量分析与扫描
        tcpdump \
        nmap \
        # 必备辅助工具
        nano \
        htop \
        less \
        mcjoin \
    && \
    # 清理 zypper 缓存和下载的包
    zypper --non-interactive clean --all && \
    # 清理 zypper 日志文件
    rm -rf /var/log/zypp/* /var/log/zypper.log

# 设置默认工作目录 (可选)
# WORKDIR /root

# 设置容器启动时默认执行的命令（启动一个交互式 bash shell）
CMD ["bash"]