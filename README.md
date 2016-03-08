# VagrantLAMP
LAMP box with mass vhost setup

## About the box 

This repository is currently set up for local development and it utilizes [Vagrant](https://www.vagrantup.com/) with 
[VirtualBox](https://www.virtualbox.org/) provider to emulate production environment on Windows, OSX and Linux (note 
that it has been tested just on Linux and OSX).

You should [read more on Vagrant](https://docs.vagrantup.com/v2/why-vagrant/index.html) if you're not familiar with it
before you proceed.

Installed on the box:
  * PHP 5.6.18
  * Apache 2.4.18
  * MariaDB 10.1.11

## Setup
  1. Install Vagrant and VirtualBox
  2. Clone this repository to your machine 
  3. From project root, run `vagrant up`
  5. Update your [hosts file](https://en.wikipedia.org/wiki/Hosts_(file)#Location_in_the_file_system) as described below

### Vhost setup
TODO
