# Feed-The-Beast Pyramid Reborn (Modded Minecraft Map 1.12) in Docker
To pull the image:
```
docker pull audiohacked/ftb_pyramid_reborn:stable
```

It's highly recommended run a named data volume:
```
docker volume create minecraft_ftb_pyramid_reborn_data
docker volume create minecraft_ftb_pyramid_reborn_backups
```

Then, run the server container:
```
docker run --detach --interactive --tty \
    --name ftb_pyramid_reborn \
    --volume minecraft_ftb_pyramid_reborn_data:/minecraft/world \
    --volume minecraft_ftb_pyramid_reborn_backups:/minecraft/backups \
    --publish 25565:25565 \
    --env EULA=TRUE \
    audiohacked/ftb_pyramid_reborn:stable
```
