# MC-server

The idea here is to spin up a Minecraft server using Spigot and MCMMO in Docker swarm. This will give you a server you can play on with friends and it will auto restart. It also ensures you can move it / back it up.

## Setup
- Install Docker
- Init the swarm `docker swarm init`
- Create the volumes
```bash
docker volume create mc-world
docker volume create mc-world-nether
docker volume create mc-world-end
```
- Create the service
```bash
docker service create --name mc --publish  25565:25565 --mount type=volume,source=mc-world,destination=/mc/world --mount type=volume,source=mc-world-nether,destination=/mc/world_nether --mount type=volume,source=mc-world-end,destination=/mc/world_the_end just1689/mc-server:1
```

