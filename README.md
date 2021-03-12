# containerized-services
A collection of Dockerfile's for hosting containerized services intended for testing a primary applications integration with them

## Rsyslog

Build with:
```bash
docker build -t containerized-services/rsyslog rsyslog/
```

Run with:
```bash
docker run --rm -p 514:514/tcp -p 514:514/udp rsyslog:latest
```
