# BL Digital Scholarship Development Box

A virtual machine configuration that installs some common development tools and navigates the annoying BL web proxy when used internally.

Includes:

- Ubuntu 14.04
- git
- Python
- PostgreSQL
- Node.js
- npm

**Note:** You will need to ensure that Virtualization is enabled in your BIOS settings.

## Installation

Download and install:
- [git](https://git-scm.com/downloads)
- [VirtualBox](https://www.virtualbox.org/)
- [Vagrant (>=1.8.0)](https://www.vagrantup.com/)

If you're on Windows 7 you should also upgrade Powershell to resolve an issue in recent versions of Vagrant where commands will hang indefinitely.

From the command line run:

``` bash
# Set environment variables (using your username and password)
set HTTP_PROXY=http://username:password@loncache.bl.uk:7070
set HTTPS_PROXY=https://username:password@loncache.bl.uk:7070
set VAGRANT_HTTP_PROXY=http://username:password@loncache.bl.uk:7070
set VAGRANT_HTTPS_PROXY=https://username:password@loncache.bl.uk:7070

# clone
git clone https://github.com/alexandermendes/vagrant-bl-digischol

# change directory
cd vagrant-bl-digischol

# install plugins
vagrant plugin install vagrant-proxyconf
vagrant plugin install vagrant-vbguest

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

If you see errors related to guest permissions when executing the last
command given above you can try:

```
vagrant reload --provision
```
