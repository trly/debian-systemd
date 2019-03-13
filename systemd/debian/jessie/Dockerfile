FROM debian:jessie

ENV LC_ALL C
ENV DEBIAN_FRONTEND noninteractive
ENV container docker

RUN apt-get update \
    && apt-get install -y systemd \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

RUN cd /lib/systemd/system/sysinit.target.wants/; \
for i in *; do [ $i = systemd-tmpfiles-setup.service ] || rm -f $i; done;\
rm -f /lib/systemd/system/multi-user.target.wants/*;\
rm -f /etc/systemd/system/*.wants/*;\
rm -f /lib/systemd/system/local-fs.target.wants/*; \
rm -f /lib/systemd/system/sockets.target.wants/*udev*; \
rm -f /lib/systemd/system/sockets.target.wants/*initctl*; \
rm -f /lib/systemd/system/basic.target.wants/*;\
rm -f /lib/systemd/system/anaconda.target.wants/*;\
update-rc.d dbus enable;

VOLUME [ "/sys/fs/cgroup" ]

CMD [ "/lib/systemd/systemd" ]