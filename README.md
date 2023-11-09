# docker-traefik

**Installation**
```shell
$ cd /opt/
$ git pull docker-traefik
$ cd docker-traefik/
$ cp .env.example .env
$ vim .env 
$ docker network create “proxy”
$ docker compose up -d
$ ln -s /opt/docker-traefik/logrotate traefik
```

**Migration**
Existing data can be migrated by copying the `appdata` directory and `.env` file.

**Known issues**
- Grafana user: https://grafana.com/docs/grafana/v9.0/setup-grafana/configure-docker/#run-grafana-container-using-bind-mounts
- Promtail data directory: https://stackoverflow.com/a/69032349
- In case Wiki.js git sync doesn't work: `cd appdata/wikijs/ && chown -R 1000:1000 .ssh/`
- Create Basic Auth user: https://httpd.apache.org/docs/2.4/programs/htpasswd.html#examples