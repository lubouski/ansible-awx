# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.define "master" do |master|
     master.vm.box = "sbeliakou/centos-7.4-x86_64-minimal"
     master.vm.hostname = "ansible"
     master.vm.network "private_network", ip: "192.168.56.10"
     master.vm.network :forwarded_port, guest: "80", host: "8080"
     master.vm.provider :virtualbox do |vb|
        vb.customize ["modifyvm", :id, "--memory", "4096"]
          end
     master.vm.provision :ansible do |ansible|
        ansible.playbook = "playbook.yml"
        ansible.verbose = "vv"
        end
  end
end
