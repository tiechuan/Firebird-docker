# command line to run firebird in docker

# create a volume
docker volume create firebird

# run the docker command
docker run \
 --name firebird257 \
 -p 3050:3050 \
 -p 13050:13050 \
 -e ISC_PASSWORD=masterkey \
 -e TZ=Australia/Melbourne \
 -d \
 --mount source=firebird,target=/firebird/data \
 jacobalberty/firebird:2.5-ss

# connect to firebird docker container 
 docker exec -it firebird257 bash
 
# connect to firdbird isql
/usr/local/firebird/bin/isql -u SYSDBA -p masterkey

# create testing database
create database '/firebird/data/test.fdb';
 