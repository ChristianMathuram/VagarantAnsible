# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

config.ssh.insert_key = false
config.vm.synced_folder ".", "/vagrant", disabled: true
config.vm.provider :vmware_desktop do |v|
  v.gui = true
v.memory = 1024
v.linked_clone = true
end

# TestA
config.vm.define "testa" do |testa|
config.vm.provider "vmware_desktop"
testa.vm.box = "hashicorp/bionic64"
testa.vm.hostname = "TestA.test"
testa.vm.network :private_network, ip: "192.168.60.4"
testa.vm.provision "Installing Ansible in TestA", type: "shell", preserve_order: true, inline: "sudo apt install -y ansible"
end

# TestB
config.vm.define "testb" do |testb|
config.vm.provider "vmware_desktop"
testb.vm.box = "hashicorp/bionic64"
testb.vm.hostname = "TestB.test"
testb.vm.network :private_network, ip: "192.168.60.5"
testb.vm.provision "Updating VM TestC", type: "shell", preserve_order: true, inline: "sudo apt update"
end

# TestC
config.vm.define "testc" do |testc|
config.vm.provider "vmware_desktop"
testc.vm.box = "hashicorp/bionic64"
testc.vm.hostname = "TestC.test"
testc.vm.network :private_network, ip: "192.168.60.6"
testc.vm.provision "Installing Tree in TestC", type: "shell", preserve_order: true, inline: "sudo apt install tree"
testc.vm.provision "Updating VM TestC", type: "shell", preserve_order: true, inline: "sudo apt update"
end

end