# Rsyslog

Build with:
```bash
docker build -t containerized-services/rsyslog rsyslog/
```

Run with:
```bash
docker run --rm -p 514:514/tcp -p 514:514/udp containerized-services/rsyslog
```