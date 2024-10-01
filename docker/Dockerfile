FROM ubuntu:24.04

RUN apt-get update && apt-get install -y \
    openssh-server \
    sudo \
    curl \
    bash \
    zsh \
    git \
    nano \
    htop \
    ncdu \
    sshpass

RUN mkdir /var/run/sshd

RUN echo 'root:rootpassword' | chpasswd

RUN echo "PermitRootLogin yes" >> /etc/ssh/sshd_config && \
    echo "PasswordAuthentication yes" >> /etc/ssh/sshd_config && \
    echo "PermitEmptyPasswords no" >> /etc/ssh/sshd_config && \
    echo "UsePAM no" >> /etc/ssh/sshd_config

EXPOSE 22 80

RUN ssh-keygen -A

CMD ["/usr/sbin/sshd", "-D"]
