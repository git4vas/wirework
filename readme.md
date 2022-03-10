# Academic project history

## Failed Steps

Installing Graylog in container over VirtualBox VM on a physical machine with HDD.

reason: HW failure

## Consequent workflow

### Management VM setup

OS: ubuntu 20.04 LTS - Mate

Software:

* VSCode
* AnyDesk

Remote machine software:
VMware Remote Console

### Log Server Setup

OS: ubuntu 20.04 LTS - Mate

Software:

* docker
* docker-compose

Containers:

* Portainer (management web-interface)
* Graylog stacked with
  * MongoDB
  * ElasticSearch

TODO

* ntp

#### docker Installation

nstall packages to allow apt to use a repository over HTTPS:

    #apt-get install \
    >     ca-certificates \
    >     curl \
    >     gnupg \
    >     lsb-release

then Add Docker’s official GPG key

    $curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg

set up the stable repository

    echo \
    "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu \
    $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

Update the `apt` package index, and install the latest version of Docker Engine and containerd

    # apt-get update
    # apt-get install docker-ce docker-ce-cli containerd.io

#### docker-compose v2 installation

    # curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose

    # chmod +x /usr/local/bin/docker-compose

#### pulling the repo

    git clone https://github.com/git4vas/wirework.git

Added .env to store the password hash
