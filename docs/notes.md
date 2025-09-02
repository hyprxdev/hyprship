

```yaml

services:
  hyprship:
    image: hyprship:latest
    hostname: hyprship
    container_name: hyprship
    deploy:
      replicas: 1
      restart_policy: always
      placement:
        constraints:
          - node.role == manager
      update_config:
        parallelism: 1
        delay: 10s
      resources:
        limits:
          cpus: '0.5'
          memory: 512M
        reservations:
          cpus: '0.25'
          memory: 256M
      labels:
        com.docker.stack.namespace: hyprship
        com.docker.stack.service: hyprship

```
