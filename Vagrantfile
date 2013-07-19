 Vagrant.configure("2") do |config|
    config.vm.box = "precise64"
    config.vm.network :private_network, ip: "192.168.111.222"

	 config.vm.network :forwarded_port, guest: 8080, host: 8080
	

    config.vm.provider "virtualbox" do |v|
       v.customize ["modifyvm", :id, "--memory", 2048]
    end

    config.vm.provision :ansible do |ansible|
      ansible.playbook = "vagrant.yml"
      ansible.inventory_file = "dev-inventory"
    end

    
    config.vm.provision :ansible do |ansible|
      ansible.playbook = "site.yml"
      ansible.inventory_file = "dev-inventory"
    end
  end
