# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  # All Vagrant configuration is done here. The most common configuration
  # options are documented and commented below. For a complete reference,
  # please see the online documentation at vagrantup.com.

  # Every Vagrant virtual environment requires a box to build off of.
  config.vm.box = "ubuntu/trusty64"

  config.vm.network "private_network", type: "dhcp"

  config.vm.provision :ansible do |ansible|
    ansible.playbook = "rails-stack.yml"
    ansible.verbose = "vvvv"
    ansible.sudo = true
  end

  config.vm.synced_folder "~", "/vagrant", :nfs => true
end
