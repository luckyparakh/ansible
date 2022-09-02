FROM centos:7

# Set this to “False” if you want to avoid host key checking by the underlying tools Ansible uses to connect to the host
ENV ANSIBLE_HOST_KEY_CHECKING False

RUN yum install epel-release -y && \
    yum update -y && \
        yum install -y openssh-server openssh-clients net-tools && \
    yum install -y ansible
CMD /bin/bash