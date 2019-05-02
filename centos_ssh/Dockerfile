FROM centos
LABEL name="jack" email="jack33891024@gmail.com"
# install epel
RUN yum install epel-release -y
# base pkgs
RUN yum install -y openssh-client openssl-devel openssh-server vim wget git tree net-tools psmisc bash-completion supervisor golang &&\
    yum clean all        
# sshd
RUN ssh-keygen -t rsa -f /etc/ssh/ssh_host_rsa_key &&\
    ssh-keygen -t ecdsa -f /etc/ssh/ssh_host_ecdsa_key &&\
    ssh-keygen -A -t dsa -f /etc/ssh/ssh_host_dsa_key
# set root password
RUN echo "123456" | passwd --stdin root
EXPOSE 22
CMD ["/usr/sbin/sshd","-D"]
