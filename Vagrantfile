# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

#Insert known pubkey into all boxes
#See the provision.yml file for instructions on using your own pubkey
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "provision.yml"
    ansible.extra_vars = { ansible_ssh_user: 'vagrant' }
  end 


  config.vm.define "debian_testing" do |debian_testing|
    debian_testing.vm.box = "fujimakishouten/debian-stretch64"
    debian_testing.vm.network "private_network", ip: "192.168.33.10"
    debian_testing.vm.provider "virtualbox" do |vb|
      vb.memory = "512"
    end
  end

  config.vm.define "debian_jessie" do |debian_jessie|
    debian_jessie.vm.box = "debian/contrib-jessie64"
    debian_jessie.vm.network "private_network", ip: "192.168.33.11"
    debian_jessie.vm.provider "virtualbox" do |vb|
      vb.memory = "512"
    end
  end

  config.vm.define "ubuntu_trusty" do |ubuntu_trusty|
    ubuntu_trusty.vm.box = "ubuntu/trusty64"
    ubuntu_trusty.vm.network "private_network", ip: "192.168.33.12"
    ubuntu_trusty.vm.provider "virtualbox" do |vb|
      vb.memory = "512"
    end
  end
  #The default xenial VM does not have a "vagrant" user 
  #Using boxcutter here saves us a lot of hackarounds.
  config.vm.define "ubuntu_xenial" do |ubuntu_xenial|
    ubuntu_xenial.vm.box = "boxcutter/ubuntu1604"
    ubuntu_xenial.vm.network "private_network", ip: "192.168.33.13"
    ubuntu_xenial.vm.provider "virtualbox" do |vb|
      vb.memory = "512"
    end
  end 
end
