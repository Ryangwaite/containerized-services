FROM ubuntu:20.04

RUN apt-get update && apt-get install --yes \
    snmp \
    snmptrapd \
    snmp-mibs-downloader

# Install common MIBs
RUN download-mibs

# Install opengear MIBs
RUN mkdir -p /usr/share/snmp/mibs/opengear/
RUN wget -P /usr/share/snmp/mibs/opengear/ \
    http://ftp.opengear.com/download/snmp/mibs/current/OG-CONNECT-MIB.mib \
    http://ftp.opengear.com/download/snmp/mibs/current/OG-DATA-MIB.mib \
    http://ftp.opengear.com/download/snmp/mibs/current/OG-FAILOVER-MIB.mib \
    http://ftp.opengear.com/download/snmp/mibs/current/OG-HOST-MIB.mib \
    http://ftp.opengear.com/download/snmp/mibs/current/OG-PATTERN-MIB.mib \
    http://ftp.opengear.com/download/snmp/mibs/current/OG-PRODUCTS-MIB.mib \
    http://ftp.opengear.com/download/snmp/mibs/current/OG-SENSOR-MIB.mib \
    http://ftp.opengear.com/download/snmp/mibs/current/OG-SIGNAL-MIB.mib \
    http://ftp.opengear.com/download/snmp/mibs/current/OG-SMI-MIB.mib \
    http://ftp.opengear.com/download/snmp/mibs/current/OG-STATUS-MIB.mib \
    http://ftp.opengear.com/download/snmp/mibs/current/OG-STATUSv2-MIB.mib \
    http://ftp.opengear.com/download/snmp/mibs/current/OG-UPS-MIB.mib \
    http://ftp.opengear.com/download/snmp/mibs/current/OGTRAP-MIB.mib \
    http://ftp.opengear.com/download/snmp/mibs/current/OGTRAPv2-MIB.mib \
    http://ftp.opengear.com/download/lighthouse/current/mibs/OG-LIGHTHOUSE-MIB.mib

# Install the config file
COPY snmptrapd.conf /etc/snmp/

# Start and log to stdout
ENTRYPOINT [ "snmptrapd", "-f", "-m", "ALL", "-L", "o" ]