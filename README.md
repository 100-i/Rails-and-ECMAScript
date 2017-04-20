Rails & Ecmascript 
==================

This is a Rails 5 project that provides a small demonstration of how ECMAScript
(ES6) can be added to the asset pipeline for Rails.

## Instructions

### 1.

Ensure [Vagrant](https://vagrantup.com/) is installed and run `vagrant up`.

~~~~~~shell
$ vagrant --version
Vagrant 1.9.3
~~~~~~

### 2.

Run `vagrant up` to start the machine and connect using `vagrant ssh`.

~~~~~~shell
$ vagrant up
Bringing machine 'default' up with 'virtualbox' provider...
==> default: Importing base box '100/ubuntu-16.10-puppet'...
...

$ vagrant ssh
Welcome to Ubuntu 16.10 (GNU/Linux 4.8.0-46-generic x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

0 packages can be updated.
0 updates are security updates.


vagrant@vagrant:~$
~~~~~~

### Detailed Information

This project uses only a handful of Gems to accomplish adding ES6 files to the
asset pipeline in Rails 5. The gems lists the gems and the additions needed to
any `Gemfile` to add ECMAScript to any Rails project.

#### Gems

The following gems provide basic support for ES6: `sprockets` and
`sprockets-es`.

~~~~~~shell
# Gemfile
gem 'sprockets'
gem 'sprockets-es6'
~~~~~~

#### Vagrant Installation

Instructions for installing Vagrant on Windows and Linux machines. More
installation options and instructions-including Mac-can be found at
https://vagrantup.com/downloads.

#### Windows

Use [Chocolatey](https://chocalety.org) for best results.

Run `choco` from a Powershell context with Adminstratitive privileges.

~~~~~~powershell
choco install vagrant -y
~~~~~~

#### Linux

The package manager for a distribution may include their own packaging of
Vagrant; but it is recommended to use a package from the Vagrant
[downloads](https://vagrantup.com/downloads) page for best results.

##### Install Vagrant in Debian

~~~~~~shell
cd /tmp
wget https://releases.hashicorp.com/vagrant/1.9.3/vagrant_1.9.3_x86_64.deb
sudo dpkg -i vagrant_1.9.3_x86_64.deb
~~~~~~
