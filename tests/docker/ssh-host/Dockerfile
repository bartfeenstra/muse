ARG FROM
FROM ${FROM}

COPY ./id_rsa.pub /root/.ssh/authorized_keys

RUN apt-get update && \
    apt-get install -y openssh-server

ENTRYPOINT mkdir -p /run/sshd && /usr/sbin/sshd -D -e
