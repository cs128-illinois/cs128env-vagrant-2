# encoding: utf-8
# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "bento/ubuntu-18.04"
  # config.ssh.forward_x11 = true
  config.vm.provider "virtualbox" do |vb|
    vb.name = "cs128@illinois-v2021b"
    vb.memory = 512
    vb.cpus = 1
    vb.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
    vb.customize ["modifyvm", :id, "--usb", "off"]
    vb.customize ["modifyvm", :id, "--usbehci", "off"]
    vb.customize ["modifyvm", :id, "--cableconnected1", "on"]
  end

  config.vm.synced_folder "lib", "/home/vagrant/lib", create: true
  config.vm.synced_folder "src", "/home/vagrant/src", create: true

  config.vm.provision "shell", path: ".config/provision.sh"
end
