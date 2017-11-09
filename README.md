# BL Digital Scholarship Development Box

A virtual machine configuration that installs some common development tools and navigates the annoying BL web proxy when used internally.

Includes:

- Ubuntu 16.04
- git
- Python
- PostgreSQL
- Node.js
- npm

**Note:** You will need to ensure that Virtualization is enabled in your BIOS settings.

## Installation

Install [VirtualBox](https://www.virtualbox.org/), [Vagrant (>=1.8.0)](https://www.vagrantup.com/), then from the command line run:

``` bash
# clone
git clone https://github.com/alexandermendes/vagrant-bl-digischol

# change directory
cd vagrant-bl-digischol

# install plugins
vagrant plugin install vagrant-proxyconf
vagrant plugin install vagrant-vbguest

# Set environment variables (using your username and password)
set HTTP_PROXY=http://username:password@loncache.bl.uk:7070
set HTTPS_PROXY=https://username:password@loncache.bl.uk:7070
set VAGRANT_HTTP_PROXY=http://username:password@loncache.bl.uk:7070
set VAGRANT_HTTPS_PROXY=https://username:password@loncache.bl.uk:7070

# create the vm
vagrant up

# enter the vm
vagrant ssh
```

## Upgrading

If this repository is updated and you want to pull in those updates run:

```
cd /path/to/vagrant-bl-digischol
git pull
vagrant up --provision
```
