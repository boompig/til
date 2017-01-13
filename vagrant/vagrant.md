# Vagrant

## Create new container & Vagrantfile

vagrant init `hashicorp/$linux_flavour`

## Boot container

vagrant up

## Software to install

It goes into `bootstrap.sh` in the same dir as `Vagrantfile`

## Reload bootstrap actions

vagrant reload --provision
