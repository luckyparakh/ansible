# Don't use centos 8
FROM centos:7 

# Install OpenSSh server and client with yum
RUN yum -y install openssh-server openssh-clients

# Created because public key is required when starting sshd
RUN ssh-keygen -f /etc/ssh/ssh_host_rsa_key -N '' -t rsa
RUN ssh-keygen -f /etc/ssh/ssh_host_ecdsa_key -N '' -t ecdsa

# Allow login as root
RUN sed -ri 's/^#PermitEmptyPasswords no/PermitEmptyPasswords yes/' /etc/ssh/sshd_config

# Specify root password
RUN echo "root:" | chpasswd

EXPOSE 22

# Start sshd
CMD ["/usr/sbin/sshd", "-D"]