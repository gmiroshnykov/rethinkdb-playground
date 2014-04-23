# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "hashicorp/precise64"

  config.ssh.forward_agent = true

  config.vm.define "db1" do |cfg|
    cfg.vm.hostname = "db1.rethinkdb.dev"
    cfg.vm.network :private_network, ip: "10.0.60.2"
  end

  config.vm.define "db2" do |cfg|
    cfg.vm.hostname = "db2.rethinkdb.dev"
    cfg.vm.network :private_network, ip: "10.0.60.3"
  end

  config.vm.define "db3" do |cfg|
    cfg.vm.hostname = "db3.rethinkdb.dev"
    cfg.vm.network :private_network, ip: "10.0.60.4"

    # only the last VM should trigger Ansible
    cfg.vm.provision :ansible do |ansible|
      ansible.limit = "all"
      ansible.playbook = "ansible/all.yml"
      ansible.inventory_path = "ansible/vagrant"
    end
  end

  config.vm.provider "virtualbox" do |v|
    v.memory = 512
  end

  if Vagrant.has_plugin?("vagrant-cachier")
    config.cache.scope = :machine
  end
end
