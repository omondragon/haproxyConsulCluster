# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  config.vm.define :haproxy do |haproxy|
     haproxy.vm.box = "bento/ubuntu-22.04-arm64"
     haproxy.vm.network :private_network, ip: "192.168.100.18"
     haproxy.vm.hostname = "haproxy"
     haproxy.vm.synced_folder "./Shared_Folder_proyect01", "/home/vagrant/Shared_Folder_proyect01"
     
     # Reenvío de puertos
     #haproxy.vm.network "forwarded_port", guest: 80, host: 80
     
     haproxy.vm.provision "shell", path: "script_haproxy.sh"
  end
  
   config.vm.define :service1 do |service1|
    service1.vm.box = "bento/ubuntu-22.04-arm64"
    service1.vm.network :private_network, ip: "192.168.100.19"
    service1.vm.hostname = "service1"
    service1.vm.synced_folder "./Shared_Folder_proyect01", "/home/vagrant/Shared_Folder_proyect01"
    
    service1.vm.provision "shell", path: "script_service1.sh"
  end
  
   config.vm.define :service2 do |service2|
    service2.vm.box = "bento/ubuntu-22.04-arm64"
    service2.vm.network :private_network, ip: "192.168.100.20"
    service2.vm.hostname = "service2"
    service2.vm.synced_folder "./Shared_Folder_proyect01", "/home/vagrant/Shared_Folder_proyect01"
    
    service2.vm.provision "shell", path: "script_service2.sh"
  end

end
