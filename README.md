# VagrantLAMP
LAMP box with mass vhost setup

## About the box 

This repository is currently set up for local development and it utilizes [Vagrant](https://www.vagrantup.com/) with 
[VirtualBox](https://www.virtualbox.org/) provider to emulate production environment on Windows, OSX and Linux (note 
that it has been tested just on Linux and OSX).

You should [read more on Vagrant](https://docs.vagrantup.com/v2/why-vagrant/index.html) if you're not familiar with it
before you proceed.

Installed on the box:
  * PHP 7.1
  * Apache 2.4
  * MariaDB 10.0
  * MongoDB 2.6
  * Redis 3.2
  * Composer

## Setup
  1. Install Vagrant and VirtualBox
  2. Clone this repository to your machine 
  3. From project root, run `vagrant up`
  5. Update your [hosts file](https://en.wikipedia.org/wiki/Hosts_(file)#Location_in_the_file_system) as described below
  6. Add your projects to `Sites` directory
  
Notes: 
 - Make sure your projects directory are lowercase because browsers will lowercase your domain, same goes for hosts file records.
 - User `ubuntu` has password `ubuntu`

## Hosts file
Append the following to your hosts file in order to load 3 examples in your browser
```
192.168.33.10   example1.local
192.168.33.10   example2.pub
192.168.33.10   example3.public_html
```

## Vhosts mapping through domain
This box utilizes [Dynamically Configured Mass Virtual Hosting by Apache](https://httpd.apache.org/docs/2.4/vhosts/mass.html).

Current box setup recognizes hostname and based of TLD decides where's the project root.

Domain without TLD (in examples above that would be `example1`, `example2` and `example3`) is the project directory name 
and everything you want to be loaded for each of the domains must live in directory `Sites/<PROJECT_DIRECTORY>/`.   

When `.local` is recognized, `Sites/<PROJECT_DIRECTORY>/` is the recognized as project root, and everything else including 
`.pub` and `.public_html` presumes that project root is a subdirectory of `<PROJECT_ROOT>` named as TLD provided. Reference 
to `Sites/example2/` and `Sites/example2/` to get the idea.

## MariaDB
Remote access to database is possible using user `dbuser` with password `toor`.
