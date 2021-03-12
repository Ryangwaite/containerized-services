# I should pin this but cant find an appropriate pinned version tag
FROM rsyslog/syslog_appliance_alpine:latest

COPY rsyslog.conf /etc/

ENTRYPOINT [ "/usr/sbin/rsyslogd", "-n"]