# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
    config.vm.box = "debian/contrib-buster64"
    config.vm.network "private_network", ip: "192.168.44.100"
    config.vm.synced_folder ".", "/vagrant", nfs: true
    config.vm.hostname = "vagrant.loc"

    config.vm.provider "virtualbox" do |vb|
        vb.name = "vagrant.loc"
        vb.memory = "2048"
        vb.cpus = 2
    end

    config.vagrant.plugins = ["vagrant-hostsupdater"]

    config.vm.provision :ansible_local do |ansible|
        ansible.playbook = "./vagrant/ansible/playbook.yml"
    end
end
