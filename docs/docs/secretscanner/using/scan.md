---
title: Scan with SecretScanner
---

# Scanning with SecretScanner

You can use SecretScanner to scan running or at-rest container images, and local file systems.  SecretScanner will match the assets it finds against the secrets rules it has been configured with.

## Scan a Container Image

Pull the image to your local repository, then scan it

```bash
docker pull node:latest

docker run -it --rm --name=khulnasoft-secretscanner \
    -v /var/run/docker.sock:/var/run/docker.sock \
    docker.io/khulnasoft/khulnasoft_secret_scanner_ce:2.2.0 \
# highlight-next-line
    --image-name node:latest

docker rmi node:latest
```

### Scan a filesystem

Mount the filesystem within the SecretScanner container and scan it.  Here, we scan the contents of `/tmp` on the host:

```bash
docker run -it --rm --name=khulnasoft-secretscanner \
# highlight-next-line
    -v /tmp:/khulnasoft/mnt \
    docker.io/khulnasoft/khulnasoft_secret_scanner_ce:2.2.0 \
# highlight-next-line
    --host-mount-path /khulnasoft/mnt --local /khulnasoft/mnt 
```

Note that you can use nerdctl as an alternative to docker in the commands above.