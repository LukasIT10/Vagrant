# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  
    config.vm.define "windows_10" do |win10|
        win10.vm.box = "Microsoft/EdgeOnWindows10"
        win10.vm.network "private_network", ip: "10.0.0.10"
    end
    config.vm.define "Ubuntu_Sever" do |ubuntu|
      ubuntu.vm.box = "ubuntu/trusty64"
      ubuntu.vm.network "private_network", ip: "10.0.0.20"
      ubuntu.vm.provider "virtualbox" do |vb|
          vb.memory = "512"
          vb.cpus = 1
      end
      ubuntu.vm.provision "shell", inline: <<-SHELL
        apt-get update
        apt-get install -y apache
      SHELL
    end
    config.vm.define "CentOS" do |centos|
      centos.vm.box = "centos/7"
      centos.vm.network "private_network", ip: "10.0.0.30"
      centos.vm.provider "virtualbox" do |vb|
          vb.memory = "1024"
          vb.cpus = 1
      end  
    end
end