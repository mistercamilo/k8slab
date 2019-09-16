# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/bionic64"

  config.vm.define :master1 do |master|
      master.vm.host_name = "k8-master1"
      master.vm.network "private_network", ip:"192.168.100.10"
      master.vm.provider :virtualbox do |vb|
          vb.customize ["modifyvm", :id, "--memory", "2048"]
          vb.customize ["modifyvm", :id, "--cpus", "2"]
      end
      master.vm.provision "shell",
        inline: "sudo apt update && sudo apt install -y python3 docker.io apt-transport-https curl"
  end

  config.vm.define :master2 do |master|
    master.vm.host_name = "k8-master2"
    master.vm.network "private_network", ip:"192.168.100.11"
    master.vm.provider :virtualbox do |vb|
        vb.customize ["modifyvm", :id, "--memory", "2048"]
        vb.customize ["modifyvm", :id, "--cpus", "2"]
    end
    master.vm.provision "shell",
      inline: "sudo apt update && sudo apt install -y python3 docker.io apt-transport-https curl"
  end

  config.vm.define :worker1 do |worker1|
      worker1.vm.host_name = "k8-worker1"
      worker1.vm.network "private_network", ip:"192.168.100.20"
      worker1.vm.provider :virtualbox do |vb|
          vb.customize ["modifyvm", :id, "--memory", "1024"]
          vb.customize ["modifyvm", :id, "--cpus", "1"]
      end
      worker1.vm.provision "shell",
        inline: "sudo apt update && sudo apt install -y python3 docker.io apt-transport-https curl"
  end

  config.vm.define :worker2 do |worker2|
    worker2.vm.host_name = "k8-worker2"
    worker2.vm.network "private_network", ip:"192.168.100.30"
    worker2.vm.provider :virtualbox do |vb|
        vb.customize ["modifyvm", :id, "--memory", "1024"]
        vb.customize ["modifyvm", :id, "--cpus", "1"]
    end
    worker2.vm.provision "shell",
      inline: "sudo apt update && sudo apt install -y python3 docker.io apt-transport-https curl"
  end
end