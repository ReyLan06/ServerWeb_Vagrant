# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  # Configuración de la primera máquina virtual
  config.vm.define "web1" do |web1|
    web1.vm.box = "ubuntu/bionic64"  # Box a utilizar
    web1.vm.network "private_network", ip: "192.168.50.11"  # Red privada
    web1.vm.hostname = "web1"  # Nombre del host
    web1.vm.synced_folder "./html", "/var/www/html"  # Carpeta compartida
    web1.vm.provider "virtualbox" do |vb|
      vb.memory = "512"  # Memoria RAM
      vb.name = "web1"  # Nombre en VirtualBox
    end
    web1.vm.provision "shell", inline: <<-SHELL
      sudo apt-get update
      sudo apt-get install -y apache2
    SHELL
  end

  # Configuración de la segunda máquina virtual
  config.vm.define "web2" do |web2|
    web2.vm.box = "ubuntu/bionic64"
    web2.vm.network "private_network", ip: "192.168.50.12"
    web2.vm.hostname = "web2"
    web2.vm.synced_folder "./html", "/var/www/html"
    web2.vm.provider "virtualbox" do |vb|
      vb.memory = "512"
      vb.name = "web2"
    end
    web2.vm.provision "shell", inline: <<-SHELL
      sudo apt-get update
      sudo apt-get install -y apache2
    SHELL
  end

end
