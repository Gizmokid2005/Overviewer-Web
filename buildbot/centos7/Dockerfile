FROM centos:7

ENV BUILDBOT_COMMIT dd6632af2

RUN yum -y update && yum -y install git rpm-build python-devel numpy python-pillow-devel && yum -y groupinstall 'Development Tools'
RUN cd /root && git clone https://github.com/buildbot/buildbot.git && cd buildbot && git checkout ${BUILDBOT_COMMIT}
RUN curl -SL 'https://bootstrap.pypa.io/get-pip.py' | python2
RUN cd /root/buildbot/slave && pip install .


ENV BUILDSLAVE_NAME diax-centos7-64
ENV BUILDSLAVE_ADMIN Andrew Chin <andrew@andrewchin.net>
ENV BUILDSLAVE_INFO Centos7 64-bit
COPY slave-start.sh /root/
CMD /root/slave-start.sh
