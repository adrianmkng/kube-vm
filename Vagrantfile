# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "centos/7"
  config.vm.host_name = "kube-master"
  config.vm.network :private_network, ip: "192.168.10.10"

  config.vm.provision :ansible do |ansible|
    ansible.playbook = "projects/kube-master/playbook.yml"
  end

  config.vm.provider :virtualbox do |vb|
    vb.customize ["modifyvm", :id, "--memory", "2048"]
  end
end
