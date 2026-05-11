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
