# Use phusion/baseimage as base image. To make your builds
# reproducible, make sure you lock down to a specific version, not to `latest`!
# See https://github.com/phusion/baseimage-docker/blob/master/Changelog.md
# for a list of version numbers.
FROM phusion/baseimage:0.9.18
MAINTAINER Alexander Mayorov <alexander@majorov.su>

# Set correct environment variables.
ENV HOME /root

# Install tools
RUN export DEBIAN_FRONTEND="noninteractive" && \
    apt-get update && \
    apt-get upgrade && \
    apt-get install -y build-essential git wget chrpath python wget && \
    apt-get clean

RUN rm -f /etc/service/sshd/down
# Regenerate SSH host keys. baseimage-docker does not contain any, so you
# have to do that yourself. You may also comment out this instruction; the
# init system will auto-generate one during boot.
#RUN /etc/my_init.d/00_regen_ssh_host_keys.sh

# Uncomment for your SSH settings
# ADD id_dsa.pub /tmp/id_dsa.pub
# RUN cat /tmp/id_dsa.pub >> /root/.ssh/authorized_keys && rm -f /tmp/id_dsa.pub


# Clean up APT when done.
RUN rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

# Use baseimage-docker's init system.
CMD ["/sbin/my_init"]

#EOF#
