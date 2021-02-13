# App-Sabnzbd

## First Time Prerequisites

1. Run [Traefik](https://github.com/HackingServerHomelab/App-Traefik)


## Running the Containers

1. Update the following volume mounts in [docker-compose.yml](./Docker/docker-compose.yml)
    * `../Data/config:/config`
    * `../Data/downloads:/downloads`
    * `../Data/incomplete-downloads:/incomplete-downloads`
2. Update the `host_whitelist` line in [sabnzbd.ini](./Config/sabnzbd.ini) with
   the appropriate FQDN.
3. Update the Traefik host label in [docker-compose.yml](./Docker/docker-compose.yml)
    * ``"traefik.http.routers.sabnzbd.rule=Host(`localhost`)"``
4. Run `docker-compose -f ./Docker/docker-compose.yml up -d`

## First Time Setup

1. Visit <https://your-ip>
2. Follow the wizard
