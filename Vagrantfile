# -*- mode: ruby -*-
# vi: set ft=ruby :
Vagrant.configure(2) do |config|
  config.vm.box = "centos/7"
  config.vm.provider "virtualbox" do |v|
          v.memory = 512
  end

  config.vm.define "ns" do |ns|
    ns.vm.network "private_network", ip: "192.168.50.10", virtualbox__intnet: "local"
    ns.vm.hostname = "ns.otus.test"
  end

  config.vm.define "client" do |client|
    client.vm.network "private_network", ip: "192.168.50.100", virtualbox__intnet: "local"
    client.vm.hostname = "client.otus.test"
  end

  config.vm.provision "ansible" do |ansible|
    ansible.verbose = "v"
    ansible.playbook = "provision.yml"
  end
end
