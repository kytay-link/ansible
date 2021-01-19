FROM centos:7

ENV ansible_user=admin
ENV ansible_version=29
ENV ansible_workspace=/opt/workspace

RUN yum install -y $(yum search ansible | grep $ansible_version | awk '{print $1}') sudo && \
yum install -y ansible && \
mkdir -p $ansible_workspace && \
useradd $ansible_user && \
usermod -aG wheel $ansible_user && \
echo "$ansible_user:$ansible_user" | chpasswd 

WORKDIR $ansible_workspace
USER admin

CMD [ "/bin/bash" ]