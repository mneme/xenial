Vagrant.configure(2) do |config|
  config.vm.box = "geerlingguy/ubuntu1604"

  config.vm.synced_folder "/Users/mneme", "/vagrant"

  config.vm.provider "virtualbox" do |vb|
    # Display the VirtualBox GUI when booting the machine
    vb.gui = true

    # Customize the amount of memory on the VM:
    vb.memory = "8096"
    vb.cpus = 4
    vb.customize ["modifyvm", :id, "--cableconnected1", "on"]
  end

  config.vm.provision "ansible" do |ansible|
    ansible.sudo = true
    ansible.verbose =  'v'
    ansible.playbook = "./playbook.yml"
  end

end

# Then run the ansible script
