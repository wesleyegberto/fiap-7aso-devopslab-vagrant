# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  ## Escolha da Box
  config.vm.box = "ubuntu/focal64"

  ## Configurações da VM
  config.vm.define 'workspace' do |workspace|

    workspace.vm.hostname = "workspace"
    workspace.vm.provider "virtualbox" do |v|
      v.name = "fiap-devopslab-vagrant"
      v.memory = 1024
      v.cpus = 2
    end

    workspace.vm.provision :ansible_local do |ansible|
      ansible.install  = true
      ansible.install_mode = "default"
      ansible.playbook = "ansible/playbook.yml"
      ansible.inventory_path = "ansible/inventory"
      ansible.verbose  = true
      ansible.limit    = "all"
    end
  end
end
