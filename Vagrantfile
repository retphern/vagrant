# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  config.vm.box = "ubuntu/trusty64"

  config.vm.network "public_network"
  config.vm.network "forwarded_port", guest: 5000, host: 5000, auto_correct: true
  config.vm.network "forwarded_port", guest: 80, host: 8081, auto_correct: true
  config.vm.network "private_network", ip: "192.168.1.3", virtualbox__intnet: "vboxnet0"

  config.vm.synced_folder "hoax-bot", "/vagrant"

  config.vm.provider "virtualbox" do |vb|
      vb.name = "Veda Machine"
  end

  config.vm.provision :shell, path: "bootstrap.sh"

end
