
# docker-electrumx

[![Build Status](https://travis-ci.org/m-schmoock/docker-electrumx.svg?branch=master)](https://travis-ci.org/m-schmoock/docker-electrumx)
[![Image Layers](https://images.microbadger.com/badges/image/mschmoock/electrumx:latest.svg)](https://microbadger.com/images/mschmoock/electrumx:latest)
[![Docker Pulls](https://img.shields.io/docker/pulls/mschmoock/electrumx.svg)](https://hub.docker.com/r/mschmoock/electrumx/)

> Run an Electrum server with one command.
> Updated electrumx versions >1.4 of lukechilds/electrumx docker container.


An easily configurable Docker image for running an Electrum server.

## Usage

```
docker run \
  -v /home/username/electrumx:/data \
  -e DAEMON_URL=http://user:pass@host:port \
  -e COIN=BitcoinSegwit \
  -p 50002:50002 \
  mschmoock/electrumx
```

If there's an SSL certificate/key (`electrumx.crt`/`electrumx.key`) in the `/data` volume it'll be used. If not, one will be generated for you.

You can view all ElectrumX environment variables here: https://github.com/kyuupichan/electrumx/blob/master/docs/environment.rst

### TCP Port

By default only the SSL port is exposed. You can expose the unencrypted TCP port with `-p 50001:50001`, although this is strongly discouraged.

### Version

You can also run a specific version of ElectrumX if you want.

```
docker run \
  -v /home/username/electrumx:/data \
  -e DAEMON_URL=http://user:pass@host:port \
  -e COIN=BitcoinSegwit \
  -p 50002:50002 \
  mschmoock/electrumx:v1.2.1
```

## License

MIT © Luke Childs, Michael Schmoock
