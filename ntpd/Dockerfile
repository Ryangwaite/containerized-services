FROM ubuntu:20.04

# Install ntp - had to set to 'noninteractive' to avoid questions about the timezone this is installed in
RUN DEBIAN_FRONTEND=noninteractive apt-get update && DEBIAN_FRONTEND=noninteractive apt-get install --yes \
    ntp

COPY ntp.conf /etc/

# I found debug (-d) the best way of logging NTP queries
ENTRYPOINT [ "/usr/sbin/ntpd", "-n", "-d"]