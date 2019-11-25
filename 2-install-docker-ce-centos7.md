# Install Docker-CE on CentOS 7 Jenkins Server

## Install needed packages first

```console
$ sudo yum install -y yum-utils device-mapper-persistent-data lvm2
```

## Configure the Docker-CE repo to yum package manager

```console
$ sudo yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
```

## Install Docker-CE

```console
$ sudo yum install docker-ce
```

## Add user to the Docker usergroup

```console
$ sudo usermod -aG docker $(whoami)
```

## Set Docker to start automatically in boot time

```console
$ sudo systemctl enable docker.service
```

## Start the Docker service

```console
$ sudo systemctl start docker.service
```

You'll see docker is running with systemctl status command.