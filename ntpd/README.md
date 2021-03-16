# ntpd

Build with:
```bash
docker build -t containerized-services/ntpd ntpd/
```

Run with:
```bash
docker run --rm -p 123:123/udp containerized-services/ntpd
```