FROM oraclelinux:8
RUN yum -y install python2-pip
RUN pip2 install netaddr
RUN pip2 install 'ansible==2.9.*'
RUN ansible-galaxy collection install oracle.oci
