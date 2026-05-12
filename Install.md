## Become a sudo user

1- Add your user in sudo group

```sh
sudo usermod -aG sudo username
```

2- Log out and log in, and check:

```sh
groups username
```

## Install git

For the latest stable version

```sh
sudo apt-get install git
```

To config your ssh key for git clone:

```sh
ssh-keygen -t ed25519 -C "your_email"
```

## Install Docker

1- Set up Docker's apt repository:

```sh
# Add Docker's official GPG key:
sudo apt update
sudo apt install ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc

# Add the repository to Apt sources:
sudo tee /etc/apt/sources.list.d/docker.sources <<EOF
Types: deb
URIs: https://download.docker.com/linux/ubuntu
Suites: $(. /etc/os-release && echo "${UBUNTU_CODENAME:-$VERSION_CODENAME}")
Components: stable
Architectures: $(dpkg --print-architecture)
Signed-By: /etc/apt/keyrings/docker.asc
EOF

sudo apt update
```

2- Install the Docker packages:

- If you want docker-compose

```sh
sudo apt install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

- If not:

```sh
sudo apt install docker-ce docker-ce-cli containerd.io docker-buildx-plugin
```

3- Verify if Docker is installed:

```sh
sudo systemctl status docker
```

## Install GNS3

The following instructions is for Ubuntu-based distributions:

```sh
sudo add-apt-repository ppa:gns3/ppa
sudo apt update                                
sudo apt install gns3-gui gns3-server
```

If you want IOU support:

```sh
sudo dpkg --add-architecture i386
sudo apt update
sudo apt install gns3-iou
```

*Note: IOU means IOS(Cisco Internetwork Operating System) in Linux.
It’s a lightweight version of Cisco Systems IOS routers/switches that runs as a Linux process instead of emulating full hardware.
IOU was created internally by Cisco for: testing configurations, training, protocol validation, automated labs.*

Finally, add your user into these groups: ubridge libvirt kvm wireshark docker

```sh
sudo usermod -aG ubridge,libvirt,kvm,wireshark,docker $(whoami)
```
