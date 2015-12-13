# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "precise64_vmware"
  config.vm.network :private_network, ip: "192.168.33.21"
  config.vm.provision :shell, :path => "install.sh"
  config.vm.synced_folder ".", "/var/www", owner: "www-data", group: "www-data", :mount_options => ["dmode=777", "fmode=666"]

  config.vm.provider :virtualbox do |vb|
    vb.customize ["modifyvm", :id, "--natdnsproxy1", "on"]
    vb.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
  end
end