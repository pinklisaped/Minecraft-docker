## Example
```bash
export version=1.21.1
export server_type=fabric

docker build -t minecraft:$version-$server_type --file $server_type/$version ./$server_type/

docker volume create world
docker volume create world_nether
docker volume create world_the_end

docker run \
       --name minecraft \
       -v world:/server/world \
       -v world_nether:/server/world_nether \
       -v world_the_end:/server/world_the_end \
       -p 25565:25565 \
       --rm -d minecraft:$version-$server_type
```


