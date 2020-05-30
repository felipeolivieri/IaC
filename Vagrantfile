$ansible = <<-SCRIPT
	apt-get update &&\
	apt-get install -y software-properties-common &&\
	apt-add-repository --yes --update ppa:ansible/ansible &&\
	apt-get install -y ansible
SCRIPT


Vagrant.configure("2") do |config|
  config.vm.provider "virtualbox" do |v|
  	v.memory = 1024
  	v.cpus = 1
  end

	  config.vm.define "ansible" do |ansible|
		ansible.vm.box = "ubuntu/bionic64"
  		ansible.vm.provider "virtualbox" do |v|
  			v.name = "Ubuntu-Ansible"
		end
		ansible.vm.network "public_network", ip: "192.168.68.94", bridge: "en0: Wi-Fi (AirPort)"
		ansible.vm.provision "shell", 
			inline: "cat /vagrant/configs/id_rsa.pub >> .ssh/authorized_keys"
		ansible.vm.provision "shell",
			inline: "cp /vagrant/configs/id_rsa /home/vagrant/.ssh && chmod 600 /home/vagrant/.ssh/id_rsa && chown vagrant:vagrant /home/vagrant/.ssh/id_rsa"
		ansible.vm.provision "shell", 
			inline: $ansible
	end

	config.vm.define "worpress" do |m|
		m.vm.box = "ubuntu/trusty64"
		m.vm.network "private_network", ip: "172.17.177.40"
		m.vm.network "public_network", ip: "192.168.68.95", bridge: "en0: Wi-Fi (AirPort)"
	end
end