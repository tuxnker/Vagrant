# Vagrant vSphere Init 

## Requirements
* Vagrant 1.6.3+
* VMware + vSphere API
* Ruby 1.9+
* libxml2, libxml2-dev, libxslt, libxslt-dev
* vagrant-vpshere provioder

## Installation

Install the vagrant vsphere provider using standard Vagrant plugin method:

```
$ vagrant plugin install vagrant-vsphere
```
More info in the provider here  [Vagrant-Vsphere-Provider](https://github.com/nsidc/vagrant-vsphere)

If you are runnning windows you will need to install rsync and ssh using mingw or cygwin and add the binaries path  to the system path

[mingw](http://sourceforge.net/projects/mingw/)
[cygwin](https://www.cygwin.com/)

Update the Vagrant init with your details



