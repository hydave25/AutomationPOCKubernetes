# -*- mode: ruby -*-
# vi: set ft=ruby :

ENV['VAGRANT_NO_PARALLEL'] = 'yes'

Vagrant.configure(2) do |config|

  config.vm.provision "shell", path: "bootstrap.sh"

  # Kubernetes Master Server
  config.vm.define "kmaster1" do |node|
  
    node.vm.box               = "generic/ubuntu2010"
    node.vm.box_check_update  = false
    node.vm.box_version       = "3.2.24"
    node.vm.hostname          = "kmaster1.example.com"

    node.vm.network "private_network", ip: "172.16.16.100"
  
    node.vm.provider :virtualbox do |v|
      v.name    = "kmaster1"
      v.memory  = 2048
      v.cpus    =  2
    end
    node.vm.provision "shell", path: "bootstrap_kmaster.sh"
  end
end
