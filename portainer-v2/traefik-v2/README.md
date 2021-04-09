# Traefik stack for docker swarm
## Usage
- open a shell on docker server then:  
```
STACK_BASE_PATH=/srv/data/docker/containers/traefik/  
mkdir -p $STACK_BASE_PATH && cd $STACK_BASE_PATH  
mkdir -p auth certs conf/dynamic conf/static logs nginx/conf nginx/html  
```
- ..
- ..
- ..

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
- see also other files in this repo

