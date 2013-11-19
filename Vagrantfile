 Vagrant.configure("2") do |config|

   config.vm.box = "precise64"
	 config.vm.network :forwarded_port, guest: 8080, host: 8080
	 config.vm.network :forwarded_port, guest: 29418 , host: 29418
	 
    config.vm.provider "virtualbox" do |v|
      v.customize ["modifyvm", :id, "--memory", 2048]
    end

    config.vm.provision :ansible do |ansible|
      ansible.playbook = "gerrit.yml"
      ansible.sudo = true
      # debug is on
      ansible.verbose = "vvvv"
    end

  end
