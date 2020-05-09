---
description: Things I do on my home's raspberry pi 3
---

# Raspberry

I'll be using this page as a documentation tool for the things I install in my Raspberry Pi. And for the sake of automation and how much I hate maintaining systems I'll do an extra effort to use docker compose.

## Index

* [Configuring the Raspberry](./#configuring-the-raspberry)
* [Programs Installed](./#programs-installed)

## Configuring the Raspberry

I've downloaded the Raspbian Buster Lite image, formatted a SD card with it, put it into the raspberry and connected a keyboard and monitor to it. \(I know there are simpler ways to allow an ssh connection, but meh\).  
  
I changed my user and password and allowed ssh connections through 

```text
sudo raspi-config
```

Going into Interfaces &gt; ssh and enabling it.  
  
After that I unplugged both the monitor and keyboard, connected the raspi to my local network via an ethernet cable and ssh'ed through a terminal on my computer with the command

```text
ssh myuser@raspberrypi.local
```

**TBD**: use ssh keys so as not to put the password everytime I connect to the raspi following this [instructions](https://www.raspberrypi.org/documentation/remote-access/ssh/passwordless.md) 

Install docker and docker compose via 

```text
# Docker
curl -sSL https://get.docker.com | sh
sudo usermod -aG docker myuser
docker run hello-world # Test

# Docker Compose
sudo apt-get install -y libffi-dev libssl-dev
sudo apt-get install -y python3 python3-pip
sudo apt-get remove python-configparser
sudo pip3 install docker-compose
```

## Programs installed

* [Pihole](pihole.md)

> Linux network-level advertisement and Internet tracker blocking application which acts as a DNS sinkhole, intended for use on a private network.
>
> [https://pi-hole.net/](https://pi-hole.net/)

