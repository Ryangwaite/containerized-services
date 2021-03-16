# Snmptrapd

Build with:
```bash
docker build -t containerized-services/snmptrapd snmptrapd/
```

The container is configured to log traps received in the `private` and `public` communities for SNMP version v2c.


Run with:
```bash
docker run --rm -p 162:162/udp containerized-services/snmptrapd
```

A good reference for sending snmp traps: https://support.nagios.com/kb/article.php?id=493
Running this from the host machine:
```bash
snmptrap -v 2c -c public localhost '' 1.3.6.1.4.1.8072.2.3.0.1 1.3.6.1.4.1.8072.2.3.2.1 i 123456
```
should result in this on the containers output:
```bash
2021-03-12 04:41:46 <UNKNOWN> [UDP: [172.17.0.1]:44109->[172.17.0.2]:162]:
iso.3.6.1.2.1.1.3.0 = Timeticks: (2560809) 7:06:48.09   iso.3.6.1.6.3.1.1.4.1.0 = OID: iso.3.6.1.4.1.8072.2.3.0.1       iso.3.6.1.4.1.8072.2.3.2.1 = INTEGER: 123456
```