#########################################################
# This Vagrantfile defines the configuration that will  #
# be used by the virtual machine module (VMM) to        #
# demonstrate the provision of the PGCGAP Environment   #
# through the implementation based on the               #
# Environment Code-First Framework                      #
# #######################################################
Vagrant.configure("2") do |config|
  
  # Define the virtual machine image
  # Ubuntu Bionic 18.04 64 bits
  config.vm.box = "hashicorp/bionic64"

  # Define the hostname and the network
  config.vm.define :ecf do |ecf_config|
    ecf_config.vm.hostname = "ecf"
    ecf_config.vm.network :private_network,
                          :ip => "192.168.33.10"

    # Define the Ansible configuration
    ecf_config.vm.provision "ansible_local" do |ansible|
        ansible.playbook = "bio_ecf.yml"
        ansible.verbose = "vvv"
    end
	
	# Define the provider (virtualbox), quantity of memory,
	# and how many CPUs will be used on the VM
	config.vm.provider "virtualbox" do |domain|
		domain.memory = 8192
		domain.cpus = 2
	end
  end
end




