# vi: set ft=ruby:
Vagrant.configure('2') do |config|
  (1..3).each do |i|
    config.vm.define "docker-#{i}" do |host|
      host.vm.box = "debian/jessie64"
      host.vm.network "public_network"
      host.vm.provider "virtualbox" do |vb|
        vb.memory = "512"
      end
      host.vm.provision 'ansible' do |ansible|
        ansible.playbook = 'playbook.yml'
      end
    end
  end
end
