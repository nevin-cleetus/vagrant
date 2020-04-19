# -*- mode: ruby -*-
# vi: set ft=ruby :

ENV['VAGRANT_NO_PARALLEL'] = 'yes'

Vagrant.configure(2) do |config|

  config.vm.provision "shell", path: "bootstrap.sh"

  # Kubernetes Master Server
  config.vm.define "docker" do |docker|
    docker.vm.box = "centos/7"
    docker.vm.hostname = "docker"
    docker.vm.network "private_network", ip: "172.42.42.100"
    docker.vm.provider "virtualbox" do |v|
      v.name = "docker"
      v.memory = 3548
      v.cpus = 2
      # Prevent VirtualBox from interfering with host audio stack
      v.customize ["modifyvm", :id, "--audio", "none"]
    end
    
  end

end