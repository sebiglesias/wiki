---
description: The current Docker Compose YAML I'm using
---

# Docker Compose YAML

## docker\_compose.yaml

```yaml
version: '3.4'
services:
    asf:
        container_name: asf
        hostname: asf
        image: justarchi/archisteamfarm
        restart: unless-stopped
        environment:
            - ASF_ARGS=--server
        ports:
            - 1242:1242
        volumes:
            - ${ROOT}/asf/sebi_asf.json:/app/config
```

## .env

```text
# Your timezone, https://en.wikipedia.org/wiki/List_of_tz_database_time_zones
TZ=America/Argentina/Buenos_Aires
# UNIX PUID and PGID, find with: id $USER
PUID=1000
PGID=1000
# The directory where data and configuration will be stored.
ROOT=/
```

