# -*- mode: ruby -*-
# vi: set ft=ruby :
# export VAGRANT_EXPERIMENTAL="disks"

Vagrant.configure("2") do |config|

config.vm.define "pxeserver" do |pxeserver|
  pxeserver.vm.box = 'bento/centos-8.4'
  pxeserver.vm.disk :disk, size: "15GB", name: "extra_storage1"

  pxeserver.vm.host_name = 'pxeserver'
  pxeserver.vm.network :private_network, 
                     ip: "10.0.0.20", 
                     virtualbox__intnet: 'pxenet'

  pxeserver.vm.network "forwarded_port", guest: 80, host: 8081

  pxeserver.vm.provider "virtualbox" do |vb|
    vb.memory = "1024"
    vb.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
  end
  
  pxeserver.vm.network :private_network, ip: "192.168.50.10", adapter: 3
   
#  pxeserver.vm.provision "ansible" do |ansible|
#        ansible.playbook = "ansible/playbooks/provision.yml"
#        ansible.inventory_path = "ansible/hosts"
#        ansible.host_key_checking = "false"
#        ansible.limit = "all"
#  end

# config used from this
# https://github.com/eoli3n/vagrant-pxe/blob/master/client/Vagrantfile

  config.vm.define "pxeclient" do |pxeclient|
    pxeclient.vm.box = 'bento/centos-8.4'
    pxeclient.vm.host_name = 'pxeclient'
    pxeclient.vm.network :private_network, ip: "10.0.0.21"
    pxeclient.vm.provider :virtualbox do |vb|
      vb.memory = "2048"
      vb.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
      vb.customize [
          'modifyvm', :id,
          '--nic1', 'intnet',
          '--intnet1', 'pxenet',
          '--nic2', 'nat',
          '--boot1', 'net',
          '--boot2', 'none',
          '--boot3', 'none',
          '--boot4', 'none'
        ]
    vb.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
    end
      # ENABLE to fix memory issues
     end
  end

end
