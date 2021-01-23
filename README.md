# Docker Wordpress LAMP Stack
Bitnami Wordpress stack with MariaDB, Portainer, Netdata, and Traefik

## Motivation

- host each service as a subdomain of a personal domain with letsencrypt
- run public maintained images with no modifications
- require minimal configuration and setup

## Features

- [Portainer](https://www.portainer.io/) is the definitive open source container management GUI for Kubernetes, Docker, Swarm and ACI.
- [Traefik](https://traefik.io/) is a modern HTTP reverse proxy and load balancer that makes deploying microservices easy.
- [WordPress](https://wordpress.org/) is the easiest way to create a free website or blog. It's a powerful hosting platform that grows with you.
- [Maria](https://mariadb.org/) Server is one of the most popular open source relational databases. It's made by the original developers of MySQL and guaranteed to stay open source.
- [Netdata](https://www.netdata.cloud/) - Troubleshoot slowdowns and anomalies in your infrastructure with thousands of metrics, interactive visualizations, and insightful health alarms.

## Initial Steps
```
mkdir -p $HOME/docker
```
```
git clone https://github.com/slochewie/traefik-lamp.git
```
```
cd $HOME/docker/traefik-lamp
```

## Direct Configuration (No Traefik reveerse proxy or autogenerated Let's Encrypt SSL certs.)

Copy `env.sample` to `.env` and populate all fields in the `COMMON` section.

Create a link in order to append `docker-compose.direct.yml` to future docker-compose commands.

```bash
ln -sf docker-compose.direct.yml docker-compose.override.yml
```

Review the merged configs by running `docker-compose config`.

## Letsencrypt Configuration (Traefik revese proxy creates Let's Encrypt SSL certs)

Copy `env.sample` to `.env` and populate all fields in the `COMMON` and `LETSENCRYPT` sections.

Create a link in order to append `docker-compose.letsencrypt.yml` to future docker-compose commands.

```bash
ln -sf docker-compose.letsencrypt.yml docker-compose.override.yml
```

Review the merged configs by running `docker-compose config`.

## Acknowledgments

I didn't create any of these docker images myself, so credit goes to the
maintainers, and the original software creators.

- https://hub.docker.com/r/portainer/portainer-ce
- https://hub.docker.com/_/traefik
- https://hub.docker.com/r/bitnami/wordpress
- https://hub.docker.com/r/bitnami/mariadb
- https://hub.docker.com/r/netdata/netdata

## Author

Aaron Wilson <https://niteowl.dev>

[![](https://cdn.buymeacoffee.com/buttons/default-blue.png)](https://www.buymeacoffee.com/slowchewie)

## License

[MIT License](./LICENSE)
