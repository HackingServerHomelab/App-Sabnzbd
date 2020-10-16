# App-Sabnzbd

## Running the Containers

1. Run `./Config/gen_certs.sh` to generate the SSL certificates (alternatively,
   add custom certs to the private folder)
2. Update the `server_name` in [nginx.conf](./Config/nginx.conf)
3. Update the following volume mounts in [docker-compose.yml](./Docker/docker-compose.yml)
    * `../Data/config:/config`
    * `../Data/downloads:/downloads`
    * `../Data/incomplete-downloads:/incomplete-downloads`
4. Update the `host_whitelist` line in [sabnzbd.ini](./Config/sabnzbd.ini) with
   the appropriate FQDN. Note, this should be the same `server_name` you set
   earlier.
5. Run `docker-compose -f ./Docker/docker-compose.yml up -d`

## First Time Setup

1. Visit <https://your-ip>
2. Follow the wizard
