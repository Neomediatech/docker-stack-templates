# docker-stack-templates

[website-stack-4-swarm.yml](website-stack-4-swarm.yml) has php-fpm official image  
[website-stack-4-swarm-debian.yml](website-stack-4-swarm-debian.yml) has php-fpm debian based image  
[website-stack-4-swarm-debian-custom-fpm.yml](website-stack-4-swarm-debian-custom-fpm.yml) has php-fpm debian based image with some additional php modules  

## setup a test environment
- create a file named env
- `set -a; . ./env ; set +a ; docker stack deploy -c docker-compose.yml stack-name`
