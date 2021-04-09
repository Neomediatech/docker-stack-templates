# Traefik stack for docker swarm
## Usage
- open a shell on docker server then:  
```
STACK_BASE_PATH=/srv/data/docker/containers/traefik/  
mkdir -p $STACK_BASE_PATH && cd $STACK_BASE_PATH  
mkdir -p auth certs conf/dynamic conf/static logs nginx/conf nginx/html  
```
- copy all files as the schema below
- set an email address at line 51 in [static/traefik.toml](static/traefik.toml) file
- add user(s) in [auth/](auth/) files
- put your default ssl certificate in [certs/](certs/) directory, if you want. If you don't do it Traefik will generate one for you.  
  **BUT**, **BUT**, keep in mind that it will reveal its identity. YHBW.
- customi\[s|z\]e line 24 and 32 in [conf/dynamic/dynamic.toml](conf/dynamic/dynamic.toml) if you need it.  
  On the bottom of the file you find a section to uncomment, if you want to use your own default certificate.
- ``` export STACK_BASE_PATH=/srv/data/docker/containers/traefik/ ; export FQDN_HOST=your-full-hostname ; docker stack deploy -c docker-compose.yml traefik```

## Environment Variables
| Name                | Description                                            | Default         |
| ------------------- | ------------------------------------------------------ | --------------- |
| FQDN_HOST           | FQDN (full hostname) used to access traefik dashboard and to create letsencrypt certificates | none |
| STACK_BASE_PATH     | base folder where to host files, must exists prior to run the stack | /srv/data/docker/containers/traefik |

## Files & Dirs
```
/srv/data/docker/containers/traefik/
├── auth
│   ├── dnsbl
│   ├── failover
│   └── htpasswd
├── certs
│   ├── acme-v2.json
│   ├── default.crt
│   └── default.key
├── conf
│   ├── dynamic
│   │   └── dynamic.toml
│   └── static
│       └── traefik.toml
├── logs
│   ├── access.log
│   ├── catch-all.log
│   ├── nginx-abuse.log
└── nginx
    ├── conf
    │   └── default.conf
    └── html
        ├── 404.html
        └── ping.html
```
## Notes
- ..

