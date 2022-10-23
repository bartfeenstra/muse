ARG FROM
FROM ${FROM}
ENV container docker

RUN apt-get update && \
    apt-get install -y --no-install-recommends \
      sudo \
      systemd \
      systemd-sysv && \
    # Clean up APT.
    apt-get clean && \
    rm -rf \
      /var/lib/apt/lists/* \
      /var/log/alternatives.log \
      /var/log/apt/history.log \
      /var/log/apt/term.log \
      /var/log/dpkg.log && \
    # Clean up unneeded systemd services.
    rm -f /lib/systemd/system/multi-user.target.wants/* && \
    rm -f /etc/systemd/system/*.wants/* && \
    rm -f /lib/systemd/system/local-fs.target.wants/* && \
    rm -f /lib/systemd/system/sockets.target.wants/*udev* && \
    rm -f /lib/systemd/system/sockets.target.wants/*initctl* && \
    rm -f /lib/systemd/system/basic.target.wants/* && \
    rm -f /lib/systemd/system/anaconda.target.wants/* && \
    # The machine-id should be generated when creating the container. This will be
    # done automatically if the file is not present, so let's delete it.
    rm -f \
      /etc/machine-id \
      /var/lib/dbus/machine-id

STOPSIGNAL SIGRTMIN+3

VOLUME ["/sys/fs/cgroup"]

CMD ["/sbin/init"]
