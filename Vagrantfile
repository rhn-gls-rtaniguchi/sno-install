# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|

  config.vm.box = "fedora/38-cloud-base"
  config.vm.box_version = "38.20230413.1"
  config.vm.hostname = "utility.lab.example.com"
  # My network wifi adapter name: wlp1s0 (which provides internet access)
  # My wired ethernet is eno1
  config.vm.network "public_network", bridge: "enp0s20f0u6u3u1"
  
  config.vm.synced_folder "../data", "/vagrant_data"

  config.vm.provider "virtualbox" do |vb|
      vb.memory = "1024"
  end
  
  config.vm.provision "ansible_local" do |ansible|
    ansible.playbook = "playbook.yml"
  end

  config.vm.provision "ansible_local" do |ansible|
    ansible.playbook = "prepare-deploy-sno1.yml"
  end


end

