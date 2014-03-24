# golang-vagrant

Ubuntu 12.04-64 with Go installed as well as Vim and all the Go plugins for Vim

## What

* Base Ubuntu Precise 12.04 64-bit VM
* Golang 64-bit distribution (installed via Chef)
* Vim
* Vim/Golang [Plugins](http://tip.golang.org/misc/vim/readme.txt)
* Soon: additional [Vim plugins](http://0value.com/my-Go-centric-Vim-setup)

## Usage

### Install Vagrant 1.5:
[http://vagrantup.com](http://vagrantup.com)

### Install VirtualBox:
[https://www.virtualbox.org/wiki/Downloads](https://www.virtualbox.org/wiki/Downloads)

### Install this box:

```
git clone git@github.com:cbumgard/golang-vagrant.git
cd golang-vagrant
vagrant up
vagrant ssh
```

### Notes

This synchronizes your home ```~``` directory on your host to to ```/host/``` on the guest VM so you can use your local code in the VM. It uses NFS to make the file sync much faster than default, and this requires you to enter your password when starting/stopping the machine. Planning to address this in the future with [this fix](https://gist.github.com/GUI/2864683), but you can disable if you want by changing the Vagrantfile from:

```config.vm.synced_folder "~/", "/host", nfs: true```

to:

```config.vm.synced_folder "~/", "/host"```
