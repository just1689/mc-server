# MC-server

The idea here is to spin up a Minecraft server using Spigot and MCMMO in Docker swarm. This will give you a server you can play on with friends and it will auto restart. It also ensures you can move it / back it up.

## Setup
- Install Docker
- Init the swarm `docker swarm init`
- Create the volumes
```bash
docker volume create mc-vol
```
- Create the service
```bash
docker service create --name mc --publish  25565:25565 --mount type=volume,source=mc-vol,destination=/mc just1689/mc-server:2
```

