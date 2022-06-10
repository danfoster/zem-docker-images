FROM centos:7



# http://bugs.python.org/issue19846
# > At the moment, setting "LANG=C" on a Linux system *fundamentally breaks Python 3*, and that's not OK.
ENV LANG C.UTF-8

RUN yum install -y centos-release-scl
RUN yum install -y rh-python38-python

ENV PATH /opt/rh/rh-python38/root/bin/:$PATH

ENTRYPOINT [ "python3.8" ] 