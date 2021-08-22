# VAGRANT
---

## VM WITH MINIMUM REQUIREMENTS

`VAGRANTFILE_API_VERSION = "2"`
`Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|`
`config.ssh.insert_key = false`
`config.vm.synced_folder ".", "/vagrant", disabled: true`
`config.vm.provider :vmware_desktop do |v|`
`  v.gui = true`
`v.memory = 1024`
`v.linked_clone = true`
`end`
`# TestA`
`config.vm.define "testa" do |testa|`
`config.vm.provider "vmware_desktop"`
`testa.vm.box = "hashicorp/bionic64"`
`testa.vm.hostname = "TestA.test"`
`testa.vm.network :private_network, ip: "192.168.60.4"`
`end`

Note: 
Memory is set to 1 GB and network is enabled
Runs only on VMWare Desktop
VM will be added to VMWare Workstation list

## UPDATE WHEN VM IS CREATED

`testb.vm.provision "Updating VM TestC", type: "shell", preserve_order: true, inline: "sudo apt update"`

## INSTALL APPLICATION WHEN VM IS CREATED

`testa.vm.provision "Installing Ansible in TestA", type: "shell", preserve_order: true, inline: "sudo apt install -y ansible"`

Note: use -y flag to acknowledge 