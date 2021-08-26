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
config.vm.network :public_network
config.vm.box = "hashicorp/bionic64"
config.vm.provider :virtualbox do |v|
  v.gui = true
v.memory = 1024
v.linked_clone = true
end

# TestA
config.vm.define "testa" do |testa|
testa.vm.hostname = "TestA.test"
testa.vm.provision "Installing Ansible in TestA", type: "shell", preserve_order: true, inline: "sudo apt install -y ansible"
end

# TestB
config.vm.define "testb" do |testb|
testb.vm.hostname = "TestB.test"
testb.vm.provision "Updating VM TestC", type: "shell", preserve_order: true, inline: "sudo apt update"
end

# TestC
config.vm.define "testc" do |testc|
testc.vm.hostname = "TestC.test"
testc.vm.provision "Installing Tree in TestC", type: "shell", preserve_order: true, inline: "sudo apt install tree"
testc.vm.provision "Updating VM TestC", type: "shell", preserve_order: true, inline: "sudo apt update"
end

end