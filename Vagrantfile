# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "Win10MSEdge"
	config.vm.guest = :windows
  config.vm.communicator = ENV['communicator'] || "winrm"
	config.winrm.username = "IEUser"
  config.winrm.password = "Passw0rd!"
  config.vm.boot_timeout = 600
  config.vm.graceful_halt_timeout = 600
	config.ssh.username="IEUser"
	config.ssh.password="Passw0rd!"
	config.ssh.insert_key = false
  config.ssh.sudo_command = ''
	config.ssh.shell = 'sh -l'

  config.vm.network :forwarded_port, guest: 3389, host: 3389
  config.vm.network :forwarded_port, guest: 5985, host: 5985, id: "winrm", auto_correct: true

  config.vm.provider "virtualbox" do |v|
   v.customize ["modifyvm", :id, "--vram", "128"]
   v.customize ["modifyvm", :id, "--memory", 2048]
   v.customize ["modifyvm", :id, "--cpus", 2]
   v.customize ["modifyvm", :id, "--graphicscontroller", "vmsvga"]
   v.customize ["modifyvm", :id, "--accelerate3d", "on"]
  end

end
