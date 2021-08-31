# VAGRANT
---

## THINGS TO INSTALL 

1. Virtual box
  * `sudo apt install virtualbox`
2. Vagrant
  * `sudo apt install vagrant`
3. Install openssh server and client
  * `sudo apt install openssh-server`
  * `sudo apt install openssh-client`
4. Plugins for Vagrant
  * `vagrant plugin install vagrant-sshfs`
5. Install ansible
  * `sudo apt-add-repository ppa:ansible/ansible`
  * `sudo apt update`
  * `sudo apt install ansible`

## VM WITH MINIMUM REQUIREMENTS

Check vagrantMini.txt file to run a VM with minimum requirements in vagrant
1. Copy everything in vagrantMini and past it into Vagrant file
2. `vagrant up` in your currrent directory terminal to start the VM

Note: 
Memory is set to 1 GB and network is enabled
Runs only on VMWare Desktop
VM will be added to VMWare Workstation list

## UPDATE WHEN VM IS CREATED

`testb.vm.provision "Updating VM TestC", type: "shell", preserve_order: true, inline: "sudo apt update"`

## INSTALL APPLICATION WHEN VM IS CREATED

`testa.vm.provision "Installing Ansible in TestA", type: "shell", preserve_order: true, inline: "sudo apt install -y ansible"`

Note: use -y flag to acknowledge 

---

# Changes Made
1. Switched from vmware to virtual box
2. Set a common provider 