# Docker manage

Usefull information for managing docker containers

## Enable restart of docker and services at boot

In each aplications that should start at boot add in  `docker-compose.yml`
```
restart: always
```

## Container retart
Cron job to reateart containers every day at 01:00 at in order to maintain the overall health of apps
```
00 01 * * * docker restart $(docker ps -q)
```

## System restart 
Cron job to restart system every Saturday 00:30 week in order to maintain the overall health the system
```
30 00 * * 6 reboot
```


