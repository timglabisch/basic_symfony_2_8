# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
    config.vm.define "proj" do |machine|
      machine.vm.box = "ubuntu/trusty64"

      machine.vm.network :private_network, ip: "192.168.10.66"

      machine.vm.hostname = "proj.local"

      machine.ssh.forward_agent = true

       machine.vm.synced_folder ".", "/opt/proj"#, type: "nfs"

      machine.vm.provider :virtualbox do |vb|
        vb.customize ["modifyvm", :id, "--memory", "4096"]
        vb.customize ["modifyvm", :id, "--natdnshostresolver1", "off"]
      end

      # Ansible provisioner
      machine.vm.provision :shell, :keep_color => true, :inline => "export PYTHONUNBUFFERED=1 && export ANSIBLE_FORCE_COLOR=1 && cd /opt/proj/ansible && ./ansible -i hosts development.yml"
    end
end