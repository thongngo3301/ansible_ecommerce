# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "centos/7"
  config.ssh.insert_key = false

  config.vm.provider "virtualbox" do |v|
    v.memory = 256
    v.linked_clone = true
  end

  # Application server
  config.vm.define "ecommerce" do |app|
    app.vm.hostname = "ecommerce"
    app.vm.network "private_network", ip: "192.168.56.69"
  end

  # Provision with Ansible
  config.vm.provision "ansible" do |ansible|
    ansible.verbose = "v"
    ansible.playbook = "playbook.yml"
  end
end
