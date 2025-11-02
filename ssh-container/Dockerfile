FROM debian:bookworm

EXPOSE 22

ENV DEBIAN_FRONTEND=noninteractive
RUN apt-get -qq update
RUN apt-get -qq install openssh-server
RUN apt-get -qq install krb5-user
RUN apt-get -qq install vim 
RUN apt-get -qq clean

# configuration for the SSH server
COPY sshd_config /etc/ssh/sshd_config
# configuration for the SSH client
COPY ssh_config /etc/ssh/ssh_config 

COPY ssh_host_dsa_key /etc/ssh/ssh_host_dsa_key
RUN mkdir -p /var/run/sshd
