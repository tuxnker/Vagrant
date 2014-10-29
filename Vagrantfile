# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "project-name"
  config.vm.provision :shell, path: "bootstrap.sh", privileged: false
  config.vm.box_url = "dummy.box"
  #config.vm.box_url = "https://oss-binaries.phusionpassenger.com/vagrant/boxes/latest/ubuntu-14.04-amd64-vbox.box"

  # Change this if you would like your VM to have a different IP.
  #config.vm.network "private_network", ip: "192.168.80.80"

  # Port forwarding
  # MySQL
  #config.vm.network :forwarded_port, guest: 3306, host: 3307
  # config.vm.network :forwarded_port, guest: 80, host: 8080

  # Folder sharing.
  # First argument is folder on your pc, second is folder on VM.
  config.vm.synced_folder "~/src/", "/home/vagrant/my_src"
  config.vm.provider :vsphere do |vsphere|
    vsphere.host = 'vcentre-host'
    vsphere.insecure = 'yes' 
    vsphere.compute_resource_name = 'Cluster-Name'
    vsphere.data_center_name = 'Dedsert'
   # vsphere.resource_pool_name = 'YOUR RESOURCE POOL'
    vsphere.template_name = 'vagrant-template'
    vsphere.vm_base_path = 'Vagrant'
    vsphere.name = 'vm-name'
    vsphere.user = 'domain\user'
    vsphere.password = 'passsword'
  end

  # Create a private network, which allows host-only access to the machine
  # using a specific IP.
  # config.vm.network :private_network, ip: "192.168.33.10"
  #The user and pass you have difined in the template 
  config.ssh.username = "vagrant"
  config.ssh.password = "vagrant"
  config.ssh.insert_key = true

  # Create a public network, which generally matched to bridged network.
  # Bridged networks make the machine appear as another physical device on
  # your network.
  # config.vm.network :public_network

  # If true, then any SSH connections made will enable agent forwarding.
  # Default value: false
  # config.ssh.forward_agent = true

  # Provider-specific configuration so you can fine-tune various
  # backing providers for Vagrant. These expose provider-specific options.
  # Example for VirtualBox:
  #
  # config.vm.provider :virtualbox do |vb|
  #   # Don't boot with headless mode
  #   vb.gui = true
  #
  #   # Use VBoxManage to customize the VM. For example to change memory:
  #   vb.customize ["modifyvm", :id, "--memory", "1024"]
  # end
  #
  # View the documentation for the provider you're using for more
  # information on available options.
end
