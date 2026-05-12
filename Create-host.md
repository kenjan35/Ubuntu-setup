## Create the Dockerfile

We use Alpine because it contains busybox by default.

*Note: BusyBox - The Swiss Army Knife of Embedded Linux*

*- Syntax:*
  busybox <applet> [arguments...]

*BusyBox combines tiny versions of many common UNIX utilities into a single small executable.*
*It provides minimalist replacements for most of the utilities you usually find in GNU coreutils, util-linux, etc.*

*You can also invoke BusyBox by issuing a command as an argument on the command line. For example, entering:*
  /bin/busybox ls*

```sh
FROM alpine:3.20.10

RUN apk add --no-cache iputils \
  iproute2 \
  tcpdump \
  curl

CMD ["/bin/sh"]
```

## Build the Docker image

Use the following command:

```sh
docker build -t alpine-host .
```

Then test it:

```sh
docker run -it alpine-host
```

To see if it's running:

```sh
docker ps
```

*Note: You must remove all container before delete image.*
