# run firebird in docker

docker run \
 --name firebird257 \
 -p 3050:3050 \
 -p 13050:13050 \
 -e ISC_PASSWORD=masterkey \
 -e TZ=Australia/Melbourne \
 -d \
 jacobalberty/firebird:2.5-ss