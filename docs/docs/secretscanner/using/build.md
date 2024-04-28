---
title: Build SecretScanner
---

# Build SecretScanner

SecretScanner is a self-contained docker-based tool. Clone the [SecretScanner repository](https://github.com/khulnasoft-lab/SecretScanner), then build:

```bash
./bootstrap.sh
docker build --rm=true --tag=docker.io/khulnasoft/khulnasoft_secret_scanner_ce:2.2.0 -f Dockerfile .
```

Alternatively, you can pull the official Khulnasoft image at `docker.io/khulnasoft/khulnasoft_secret_scanner_ce:2.2.0`:

```bash
docker pull docker.io/khulnasoft/khulnasoft_secret_scanner_ce:2.2.0
```