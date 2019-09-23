
Vagrant.configure("2") do |config|
    # boxes at https://vagrantcloud.com/search.
    config.vm.box = "bento/ubuntu-16.04"
  
    # config.vm.box_check_update = false
  
    # config.vm.network "forwarded_port", guest: 80, host: 8080
    config.vm.network "forwarded_port", host_ip: "127.0.0.1", guest: 3841, host: 3841
    config.vm.network "forwarded_port", host_ip: "127.0.0.1", guest: 3842, host: 3842
  
    # config.vm.network "private_network", ip: "192.168.33.10"
  
    # config.vm.network "public_network"
  
    config.vm.synced_folder ".", "/vagrant_data"
  
    # config.vm.provider "virtualbox" do |vb|
    #   # Display the VirtualBox GUI when booting the machine
    #   vb.gui = true
    #
    #   # Customize the amount of memory on the VM:
    #   vb.memory = "1024"
    # end
   
    config.vm.provision "shell", inline: <<-SHELL
      apt-get update
      apt-get install -y apache2
    SHELL
    config.vm.provision "shell", path: "bootstrap.sh"
  end
  