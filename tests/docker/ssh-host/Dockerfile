ARG FROM
FROM muse-test-base-host-${FROM}

COPY ./id_rsa.pub /root/.ssh/authorized_keys

RUN apt-get update && \
    apt-get install -y --no-install-recommends \
      openssh-server && \
    apt-get clean && \
    rm -rf \
      /var/lib/apt/lists/* \
      /var/log/alternatives.log \
      /var/log/apt/history.log \
      /var/log/apt/term.log \
      /var/log/dpkg.log
