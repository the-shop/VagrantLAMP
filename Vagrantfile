# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "the-shop/GenericLAMP"

  config.vm.box_check_update = true 

  config.vm.network "forwarded_port", guest: 3306, host: 13306

  config.vm.network "private_network", ip: "192.168.33.10"

  config.ssh.username = "ubuntu"
  config.ssh.password = "ubuntu"

  config.vm.synced_folder "./Sites", "/var/www",
    :owner=> 'ubuntu', :group=>'www-data', :mount_options => ['dmode=775', 'fmode=775']

  config.vm.provider "virtualbox" do |vb|
    vb.memory = "2048"
  end
end
