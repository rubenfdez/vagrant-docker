# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.provider "virtualbox" do |v|
    v.memory = 4096
    v.cpus = 2
  end

  # https://vagrantcloud.com/search.
  config.vm.box = "centos/7"
  # config.vm.box_check_update = false
  config.vm.network "forwarded_port", guest: 8080, host: 18080 # HTTPD
  config.vm.network "forwarded_port", guest: 9200, host: 19200 # ELASTICSEARCH
  config.vm.network "forwarded_port", guest: 9300, host: 19300 # ELASTICSEARCH TCP
  config.vm.network "forwarded_port", guest: 5000, host: 15000 # LOGSTASH TCP
  config.vm.network "forwarded_port", guest: 5601, host: 15601 # KIBANA

  config.vm.network "public_network", bridge: "wlp1s0"
  config.vm.synced_folder "dockerfiles", "/opt/dockerfiles"

  config.vm.provision "shell", path: "script.sh"
end
