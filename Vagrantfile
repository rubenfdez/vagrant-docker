# -*- mode: ruby -*-
# vi: set ft=ruby :


Vagrant.configure("2") do |config|
  # https://vagrantcloud.com/search.
  config.vm.box = "centos/7"
  # config.vm.box_check_update = false
  config.vm.network "forwarded_port", guest: 8080, host: 18080
  config.vm.network "forwarded_port", guest: 5044, host: 15044
  config.vm.network "forwarded_port", guest: 9600, host: 19600
  # config.vm.usable_port_range = 8000..8999
  # config.vm.network "forwarded_port", guest: 80, host: 8080, host_ip: "127.0.0.1"
  # config.vm.network "private_network", ip: "192.168.33.10"
  config.vm.network "public_network", bridge: "wlp1s0"
  config.vm.synced_folder "dockerfiles", "/opt/dockerfiles"

  # config.vm.provider "virtualbox" do |vb|
  #   # Display the VirtualBox GUI when booting the machine
  #   vb.gui = true
  #
  #   # Customize the amount of memory on the VM:
  #   vb.memory = "1024"
  # end

  # config.vm.provision "shell", inline: <<-SHELL
  #   apt-get update
  #   apt-get install -y apache2
  # SHELL

  #config.vm.provision "shell", path: "https://get.docker.com/"
  config.vm.provision "shell", path: "script.sh"
end
