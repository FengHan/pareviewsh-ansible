# -*- mode: ruby -*-
# vi: set ft=ruby :
Vagrant.configure(2) do |config|
  config.ssh.insert_key = false
  config.vm.box_url = "http://192.168.3.127/ubuntu.trusty64.box"
  config.vm.define "vagrant1" do |vagrant1|
    vagrant1.vm.box = "ubuntu/trusty64"
    vagrant1.vm.hostname="vagrant1"
    vagrant1.vm.synced_folder ".", "/vagrant"
    vagrant1.vm.network "private_network", ip: "192.168.33.1"
    vagrant1.vm.network "forwarded_port", guest: 80, host: 8080
    vagrant1.vm.network "forwarded_port", guest: 443, host: 8443
  end
end
