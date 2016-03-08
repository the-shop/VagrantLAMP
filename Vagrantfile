# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "the-shop/GenericLAMP"

  config.vm.box_check_update = true 

  config.vm.network "forwarded_port", guest: 3306, host: 3306

  config.vm.network "private_network", ip: "192.168.33.10"

  config.vm.synced_folder "./Sites", "/var/www/BoxData/GenericLAMP"

  config.vm.provider "virtualbox" do |vb|
    vb.memory = "1024"
  end
end
