Vagrant::Config.run do |config|
	# Setup the virtual machine
	config.vm.box = "ubuntu/trusty64"
	config.vm.host_name = "dev-environment.local"

	# Forward port 80 for web
	config.vm.forward_port 80, 80

	# Forward port 3306 for MySQL
	config.vm.forward_port 3306, 3306

	# Uncomment to view vm in gui mode
	#config.vm.boot_mode = :gui

	# Run puppet
	config.vm.provision :puppet do |puppet|
		puppet.manifests_path = "manifests"
		puppet.manifest_file  = "setup.pp"
	end
end
