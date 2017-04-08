Vagrant.configure("2") do |config|
  config.vm.box = "bento/centos-7.3"
  config.vm.hostname = "my-vm"
  config.vm.network "private_network", ip: "192.168.100.31"
  config.vm.network "forwarded_port", guest: 80, host:80, host_ip: "127.0.0.1"
  config.vm.provision "shell", inline:"sudo yum install -y epel-release && sudo yum -y install ansible"
  config.vm.provision "shell", inline: "sudo ansible-playbook -c local /vagrant/ansible/setup.yml"
end
