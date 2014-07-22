# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  config.vm.box = "trusty64"
  config.vm.box_url = "https://vagrantcloud.com/ubuntu/trusty64/version/1/provider/virtualbox.box"

  config.ssh.forward_agent = true

  # Create a private network, which allows host-only access to the machine
  # using a specific IP.
  config.vm.network :private_network, ip: "192.168.111.222"
  config.vm.hostname = "myapp.local"
  config.hostsupdater.remove_on_suspend = false

  #syncs entire project directory to ~/application on target machine
  config.vm.synced_folder ".", "/home/vagrant/application"

  config.vm.provider "virtualbox" do |v|
    v.customize ["modifyvm", :id, "--memory", "1024"]
  end

  #provisions the environment
  config.vm.provision "ansible" do |ansible|
    ansible.raw_arguments = "-i provisioning/hosts"
    ansible.playbook = "provisioning/mean.yml"
    # ansible.verbose = 'vvvv'
  end

end
