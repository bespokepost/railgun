Docker container for CloudFlare Railgun
-----
[![Docker Stars](https://img.shields.io/docker/stars/trozz/railgun.svg)]()   [![Docker Pulls](https://img.shields.io/docker/pulls/trozz/railgun.svg)]()

example docker-compose file
```
version: '2'
services:
  railgun:
    image: trozz/railgun
    depends_on:
      - memcache
    links:
      - memcache:memcache
    ports:
      - "2408:2408"
    environment:
      - TOKEN=XXX
      - HOST=1.2.3.4
      - LOG_LEVEL=5
      - MEMCACHIER_SERVERS=localhost:11211
    volumes:
      - /var/log/docker/railgun:/var/log/railgun
  memcache:
    image: memcached
```


** To expand on Docs **
