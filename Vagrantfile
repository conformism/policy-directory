# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
#  config.vm.box = "chenhan/ubuntu-mate-desktop-18.04"
  config.vm.box = "generic/ubuntu1804"
  config.vm.hostname = "ubunwan"

  config.vm.network "private_network", ip: "192.168.18.9"
  config.ssh.insert_key = true
  config.vm.synced_folder "./data", "/data"
  config.vm.provider "libvirt" do |lv|
    lv.memory = "1024"
  end
#  config.vm.provision "shell", inline: <<-SHELL
#    apt update
#    apt upgrade
#    SHELL
  config.vm.provision :ansible do |ansible|
    ansible.compatibility_mode = "2.0"
    ansible.playbook = "provisioning/playbook.yaml"
  end

end
