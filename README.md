# traefik-lamp

## Wordpress LAMP Stack with Traefik reverse proxy and Let's Encryupt SSL certificate generation.

- https://hub.docker.com/_/traefik
- https://hub.docker.com/r/bitnami/wordpress

mkdir -p $HOME/docker

git clone https://github.com/slochewie/traefik-lamp.git

cd $HOME/docker/traefik-lamp

## Direct Configuration

Copy `env.sample` to `.env` and populate all fields in the `COMMON` section.

Create a link in order to append `docker-compose.direct.yml` to future docker-compose commands.

```bash
ln -sf docker-compose.direct.yml docker-compose.override.yml
```

Review the merged configs by running `docker-compose config`.

## Letsencrypt Configuration

Copy `env.sample` to `.env` and populate all fields in the `COMMON` and `LETSENCRYPT` sections.

Create a link in order to append `docker-compose.letsencrypt.yml` to future docker-compose commands.

```bash
ln -sf docker-compose.letsencrypt.yml docker-compose.override.yml
```

Review the merged configs by running `docker-compose config`.
