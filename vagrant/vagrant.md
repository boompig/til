# Vagrant

## Create new container & Vagrantfile

vagrant init `hashicorp/$linux_flavour`

fill in your favourite `$linux_flavour`

## Boot container

vagrant up

## Software to install

It goes into `bootstrap.sh` in the same dir as `Vagrantfile`

**NOTE** don't forget to add `-y` switch to apt-get

## Reload bootstrap actions

vagrant reload --provision

Have to add this to Vagrantfile:

```
config.vm.provision :shell, path: "bootstrap.sh"
```

## Connect to box

vagrant ssh

## Port-forwarding

Add to Vagrantfile:

```
config.vm.network :forwarded_port, guest:$guest_port, host: $host_port
```

fill in `$guest_port` and `$host_port`

## Destroy

vagrant destroy
