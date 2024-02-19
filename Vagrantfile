# -*- mode: ruby -*-
# vi: set ft=ruby :
require_relative 'provisioning/vbox.rb'
VBoxUtils.check_version('7.0.14')
Vagrant.require_version ">= 2.4.1"

BOX_NAME = "xxx2324/jammy64"
MANAGER_HOSTNAME = "xxx2324-docker"
WORKER_HOSTNAME = "xxx2324-docker-worker"

Vagrant.configure("2") do |config|
  config.vm.box = BOX_NAME

  # Configure hostmanager and vbguest plugins
  config.hostmanager.enabled = true
  config.hostmanager.manage_host = true
  config.hostmanager.manage_guest = true
  config.vbguest.auto_update = false

  # Manager node
  config.vm.define "manager", primary: true do |manager|
    manager.vm.hostname = MANAGER_HOSTNAME
    manager.vm.network "private_network", ip: "192.168.56.10"
    manager.vm.network "forwarded_port", guest: 80, host: 8080

    manager.vm.provider "virtualbox" do |prov|
        prov.name = "AISI-P2-#{manager.vm.hostname}"
        prov.cpus = 1
        prov.memory = 1024
	prov.gui = false
    end
  end
  
  # Worker node
  config.vm.define "worker" do |worker|
    worker.vm.hostname = WORKER_HOSTNAME
    worker.vm.network "private_network", ip: "192.168.56.11"
    worker.vm.network "forwarded_port", guest: 80, host: 9090
            
    worker.vm.provider "virtualbox" do |prov|
	prov.name = "AISI-P2-#{worker.vm.hostname}"
        prov.cpus = 1
        prov.memory = 1024
	prov.gui = false
    end
  end
end
