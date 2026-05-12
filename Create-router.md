## Documentation

[Quagga](https://openmaniak.com/fr/quagga_tutorial.php) or [FRRouting](https://frrouting.org/doc/)

*Note: FRR is a fork of Quagga with: active development, better protocol support, bug fixes, modern features.*

## Create the Dockerfile

```sh
FROM alpine:3.20.10

RUN apk add --no-cache frr \
  iproute2 \
  iputils \
  tcpdump \
  curl

CMD ["/bin/sh"]
```
