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

*Note: iproute2 contains: ip, ss(socket statics), tc(trafiic control), bridge(bridge configuration), ip rule.*
*iputils contains: ping, arping, tracepath, clockdiff.*
*tcpdump: network packet capture tool*

## Add inet addr

To add an IP address to interface eth0:

```sh
sudo ip addr add ip_address/mask dev eth0
```

Activate the interface:

```sh
sudo ip link set eth0 up
```

## Set up the bridge and vxlan

Create bridge

```sh
ip link add br0 type bridge
```

Activate br0 interface

```sh
ip link set br0 up
```

Create vxlan in eth0

```sh
ip link add vxlan10 type vxlan ip 10 dev eth0 remote ip_address_other/mask dstport 4789
```

Activate vxlan10 interface

```sh
ip link set vxlan10 up
ip link set vxlan10 master br0
```
