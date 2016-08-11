# -*- mode: ruby -*-
# vi: set ft=ruby :

# one instance only
#VAGRANTFILE_API_VERSION = "2"

#Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
#  config.vm.box = "ubuntu/trusty64"
#  config.vm.host_name = "cassandra-spark"
#  config.vm.network :private_network, ip: "192.168.10.11"
#  config.vm.network :forwarded_port, guest: 22, host: 1233

#  config.vm.provision :ansible do |ansible|
#    ansible.playbook = "playbook.yml"
#  end

#  config.vm.provider :virtualbox do |vb|
#    vb.customize ["modifyvm", :id, "--memory", "3096"]
#    vb.cpus = 2
#  end
#end


# three instances
Vagrant.configure("2") do |config|
N = 3
(1..N).each do |machine_id|
  config.vm.box = "ubuntu/trusty64"
  config.vm.define "node#{machine_id}" do |machine|
    machine.vm.hostname = "node#{machine_id}"
    machine.vm.network "private_network", ip: "192.168.56.#{10+machine_id}"
    if machine_id == N
      machine.vm.provision :ansible do |ansible|
        ansible.limit = "all"
        ansible.playbook = "playbook.yml"
       config.vm.provider "virtualbox" do |vb|
         vb.customize ["modifyvm", :id, "--memory", "3096"]
       end
      end
    end
  end
end
end

