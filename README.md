# Docker manage

Usefull information for managing docker containers

## Enable restart of docker and services at boot

In each aplications that should start at boot add in  `docker-compose.yml`
```
restart: always
```

## Container retart
Cron job to reateart containers at least once per day in order to maintain the overall health of apps

## System retart 
Cron job to reateart containers at least once per week in order to maintain the overall health the system


