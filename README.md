# docker-blockbook-bitzeny

Blockbook Dockerfile for BitZeny

## Usage (directly from Docker Hub)

```
docker run \
    --hostname blockbook \
    -it \
    -v "$(PWD)/db:/blockbook/db" \
    -p 9195:9195 \
    -e RPC_USER=user \
    -e RPC_PASS=pass \
    -e RPC_HOST=127.0.0.1 \
    -e RPC_PORT=9252 \
    -e MQ_PORT=38395 \
    -e TZ=Asia/Tokyo \
    bellflower2015/blockbook-bitzeny
```

Blockbook config directory is `/blockbook/config` and database directory is `/blockbook/db`.

You can set environment variables `RPC_USER`, `RPC_PASS`, `RPC_HOST`, `RPC_PORT`, and `MQ_PORT`, and also set `TZ` to change timezone.

If you want to change hostname displayed, you can set it by `--hostname`.

## Build and run instructions

### Build image

Get source code and make docker image:

```
git clone https://github.com/BitzenyCoreDevelopers/docker-blockbook-bitzeny.git
cd docker-blockbook-bitzeny
docker build -t blockbook-bitzeny .
```

Docker images are based on Debian 9 (Stretch).

### Run image

Boot from the built image as described below:

```
docker run [options] blockbook-bitzeny
```
