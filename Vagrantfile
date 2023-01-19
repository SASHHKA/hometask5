# -*- mode: ruby -*-
# vi: set ft=ruby : 
 Vagrant.configure("2") do |config|

  config.vm.define "centos" do |centos|
  centos.vm.box = "centos/7" 

   config.vm.synced_folder ".", "/vagrant"

   centos.vm.network "forwarded_port", guest: 80, host: 8080
end

   config.vm.provision "shell", inline: <<-SHELL
	mkdir /etc/folder1
	mkdir /etc/folder2
	cp /vagrant/filemover.service /etc/systemd/system
	cp /vagrant/mover.sh /usr/bin
	
	sudo systemctl start filemover.service
	 
   SHELL
end