# Vagrant

## Create new container & Vagrantfile

```
vagrant init $box
```

Fill in your favourite `$box` from [here](https://atlas.hashicorp.com/boxes/search)

## Boot container

`vagrant up`

## Software to install

It goes into `bootstrap.sh` in the same directory as `Vagrantfile`

**NOTE** don't forget to add `-y` switch to apt-get

## Reload bootstrap actions

`vagrant reload --provision`

Have to add this to Vagrantfile:

```
config.vm.provision :shell, path: "bootstrap.sh"
```

## Connect to box

`vagrant ssh`

## Port-forwarding

Add to Vagrantfile:

```
config.vm.network :forwarded_port, guest:$guest_port, host: $host_port
```

Fill in `$guest_port` and `$host_port`

## Syncing folders

By default the directory with `Vagrantfile` is called the project directory and is synced to Vagrant in the `/vagrant` directory

## Destroy

`vagrant destroy`
