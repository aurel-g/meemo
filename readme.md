# Meemo on Docker

Lightweight Meemo 1.9.0 server with database on Docker with docker-compose.

Manage your todo list, bookmarks and data in the Markdown format with [**Meemo**](https://github.com/nebulade/meemo).

[![Docker Meemo](https://github.com/qdm12/meemo/raw/master/readme/title.png)](https://hub.docker.com/r/qmcgaw/meemo/)

Docker build:
[![Build Status](https://travis-ci.org/qdm12/meemo.svg?branch=master)](https://travis-ci.org/qdm12/meemo)
[![Docker Build Status](https://img.shields.io/docker/build/qmcgaw/cloudflare-dns-server.svg)](https://hub.docker.com/r/qmcgaw/cloudflare-dns-server)

Meemo build (external):
[![Build Status](https://travis-ci.org/nebulade/meemo.svg?branch=master)](https://travis-ci.org/nebulade/meemo)

[![GitHub last commit](https://img.shields.io/github/last-commit/qdm12/cloudflare-dns-server.svg)](https://github.com/qdm12/cloudflare-dns-server/commits)
[![GitHub commit activity](https://img.shields.io/github/commit-activity/y/qdm12/cloudflare-dns-server.svg)](https://github.com/qdm12/cloudflare-dns-server/commits)
[![GitHub issues](https://img.shields.io/github/issues/qdm12/cloudflare-dns-server.svg)](https://github.com/qdm12/cloudflare-dns-server/issues)

[![Docker Pulls](https://img.shields.io/docker/pulls/qmcgaw/cloudflare-dns-server.svg)](https://hub.docker.com/r/qmcgaw/cloudflare-dns-server)
[![Docker Stars](https://img.shields.io/docker/stars/qmcgaw/cloudflare-dns-server.svg)](https://hub.docker.com/r/qmcgaw/cloudflare-dns-server)
[![Docker Automated](https://img.shields.io/docker/automated/qmcgaw/cloudflare-dns-server.svg)](https://hub.docker.com/r/qmcgaw/cloudflare-dns-server)

[![Image size](https://images.microbadger.com/badges/image/qmcgaw/meemo.svg)](https://microbadger.com/images/qmcgaw/meemo)
[![Image version](https://images.microbadger.com/badges/version/qmcgaw/meemo.svg)](https://microbadger.com/images/qmcgaw/meemo)

| Image size | RAM usage | CPU usage |
| --- | --- | --- |
| 115MB | 70MB | Very low |

It is based on:

- [Meemo](https://github.com/nebulade/meemo) and its NodeJS dependencies
- [Alpine 3.8](https://alpinelinux.org)
- [NodeJS](https://pkgs.alpinelinux.org/package/v3.8/main/x86_64/nodejs)

It also depends on a MongoDB database which is launched with Docker Compose.

## Setup

[![Docker container](https://github.com/qdm12/meemo/raw/master/readme/docker.png)](https://www.docker.com/)

1. Make sure you have [Docker](https://docs.docker.com/install) and [Docker-Compose](https://docs.docker.com/compose/install) installed
1. On your host machine, create the following:
    - The users file `users.json`
    - The data directory `data/`
    - The database directory `database/`
1. Download [**docker-compose.yml**](https://raw.githubusercontent.com/qdm12/meemo/master/docker-compose.yml) on your host, modify it as you wish:

    ```sh
    wget https://raw.githubusercontent.com/qdm12/meemo/master/docker-compose.yml
    vi docker-compose.yml
    ```

1. Launch the MongoDB database and Meemo container with

    ```sh
    docker-compose up -d
    ```

1. You can now access Meemo at [localhost:3000](localhost:3000) (depending on your port in docker-compose.yml)

## Configuration

For your convenience, a shell script [**commands.sh**](https://raw.githubusercontent.com/qdm12/meemo/master/commands.sh) can be executed on your host

The following options are provided:

- List users

    ```sh
    ./commands.sh ls
    ```

- Add user

    ```sh
    ./commands.sh add username password
    ```

- Edit user

    ```sh
    ./commands.sh edit username password
    ```

- Remove user

    ```sh
    ./commands.sh remove username
    ```

All the changes are saved to `users.json`

### Environment variables


## TODOs

- [ ] Environment variables table
- [ ] org.label-schema.docker.params
- [ ] Rework commands.sh
- [ ] Non root user
- [ ] Healthcheck
- [ ] Mail environment variables & test
- [ ] LDAP environment variables & test
- [ ] Build binary meemo + Scratch container

## License

This repository is under an [MIT license](https://github.com/qdm12/meemo/master/license)
