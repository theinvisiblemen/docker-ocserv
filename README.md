# About this docker image

This is a custom Docker image for [ocserv](http://www.infradead.org/ocserv/) which is a SSL VPN server.

It is based on alpine 3.12 and ocserv 1.0.1

## Build docker image

```bash
$ docker build -t ocserv https://github.com/blackgiulia/docker-ocserv.git
```

## Run docker container

```bash
$ docker run --name ocserv --privileged -p 443:443 -p 443:443/udp -d ocserv
```

### Add user

```bash
$ docker exec -ti ocserv ocpasswd -c /etc/ocserv/ocpasswd <username>
$ Enter password:
$ Re-enter password:
```

### Delete user

```bash
$ docker exec -ti ocserv ocpasswd -c /etc/ocserv/ocpasswd -d <username>
```
