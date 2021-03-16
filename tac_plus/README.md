# tac_plus

Build with:
```bash
docker build -t containerized-services/tac_plus tac_plus/
```

Run with:
```bash
docker run --rm -p 49:49 -v $(realpath tac_plus/tac_plus.conf):/etc/tacacs+/tac_plus.conf containerized-services/tac_plus
```