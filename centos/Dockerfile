FROM centos

RUN wget https://s3.amazonaws.com/pe-builds/released/3.1.1/puppet-enterprise-3.1.1-el-6-x86_64.tar.gz
RUN tar zxvf puppet-enterprise-3.1.1-el-6-x86_64.tar.gz
RUN wget https://raw.github.com/croomes/dockerfiles/master/pe-agent.answer
RUN puppet-enterprise-3.1.1-el-6-x86_64/puppet-enterprise-installer -a pe-agent.answer
RUN /opt/puppet/bin/puppet agent -tv
RUN chkconfig mcollective on
RUN chkconfig puppet on
RUN umount /mnt

ENTRYPOINT ["mcollective"]
EXPOSE 61613
