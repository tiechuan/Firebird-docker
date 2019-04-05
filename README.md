# run firebird in docker

docker volume create firebird

docker run \
 --name firebird257 \
 -p 3050:3050 \
 -p 13050:13050 \
 -e ISC_PASSWORD=masterkey \
 -e TZ=Australia/Melbourne \
 -d \
 --mount source=firebird,target=/firebird/data \
 jacobalberty/firebird:2.5-ss
 
 docker exec -it firebird257 bash
 
 /usr/local/firebird/bin/isql -u SYSDBA -p masterkey
 