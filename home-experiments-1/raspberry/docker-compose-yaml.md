---
description: The current Docker Compose YAML I'm using
---

# Docker Compose YAML

```text
version: '1.0'
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
        
        
```

