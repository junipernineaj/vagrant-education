# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.

Vagrant.configure("2") do |config|

  # The most common configuration options are documented and commented below.
  # For a complete reference, please see the online documentation at
  # https://docs.vagrantup.com.

  # Every Vagrant development environment requires a box. You can search for
  # boxes at https://vagrantcloud.com/search.
  config.vm.box = "ubuntu/bionic64"

  # The url from where the 'config.vm.box' box will be fetched if it
  # doesn't already exist on the user's system.

  config.vm.box_url = "http://files.vagrantup.com/precise64.box"

  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine. In the example below,
  # accessing "localhost:8080" will access port 80 on the guest machine.
  # NOTE: This will enable public access to the opened port
  # config.vm.network "forwarded_port", guest: 80, host: 8080

config.vm.network "forwarded_port", guest: 80, host: 8081

  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine and only allow access
  # via 127.0.0.1 to disable public access
  # config.vm.network "forwarded_port", guest: 80, host: 8080, host_ip: "127.0.0.1"

  # Create a private network, which allows host-only access to the machine
  # using a specific IP.
  # config.vm.network "private_network", ip: "192.168.33.10"

  # Create a public network, which generally matched to bridged network.
  # Bridged networks make the machine appear as another physical device on
  # your network.
  # config.vm.network "public_network"

  # Share an additional folder to the guest VM. The first argument is
  # the path on the host to the actual folder. The second argument is
  # the path on the guest to mount the folder. And the optional third
  # argument is a set of non-required options.
  # config.vm.synced_folder "../data", "/vagrant_data"

config.vm.synced_folder "/testmount", "/vagrant_data"

  # Provider-specific configuration so you can fine-tune various
  # backing providers for Vagrant. These expose provider-specific options.
  # Example for VirtualBox:
  #
  #   # Display the VirtualBox GUI when booting the machine
  #   # Customize the amount of memory on the VM:
  #
config.vm.provider "virtualbox" do |vb|
vb.gui = false
vb.memory = "4096"
vb.cpus = 2
end
  #
  # View the documentation for the provider you are using for more
  # information on available options.

  # Enable provisioning with a shell script. Additional provisioners such as
  # Puppet, Chef, Ansible, Salt, and Docker are also available. Please see the
  # documentation for more information about their specific syntax and use.

config.puppet_install.puppet_version = :latest

# Configure with inline commands

config.vm.provision "shell", inline: "apt-get update"
config.vm.provision "shell", inline: "apt-get install -y apache2"
config.vm.provision "shell", inline: "rm -rf /var/www"
config.vm.provision "shell", inline: "ln -fs /vagrant /var/www"

# Configure Apache with a Shell Script
#config.vm.provision "shell", path: "provision.sh"

# Configure Apache with Chef
#config.vm.provision "chef_solo" do |chef|
#chef.version = "14.12.9"
#chef.add_recipe "vagrant_book"
#end

# Configure Apache with Puppet
#config.vm.provision "puppet"

end