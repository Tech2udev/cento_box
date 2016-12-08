# -*- mode: ruby -*-
# vi: set ft=ruby :

# The parameter for 2 is Vagrant "2" configuration type
Vagrant.configure("2") do |config|
  # Base box based on https://atlas.hashicorp.com/Gigasavvy/boxes/centos7-LAMP
  config.vm.box = "Gigasavvy/centos7-LAMP"

  # Disable automatic box update checking. If you disable this, then
  # boxes will only be checked for updates when the user runs
  # `vagrant box outdated`. This is not recommended.
  # config.vm.box_check_update = false

  # accessing "localhost:8080" will access port 80 on the guest machine.
   config.vm.network "forwarded_port", guest: 80, host: 8080

  # Create a private network, which allows host-only access to the machine
  # using a specific IP.
   config.vm.network "private_network", ip: "192.168.33.10"

  # Create a public network, which generally matched to bridged network.
  # Bridged networks make the machine appear as another physical device on
  # your network.
  # config.vm.network "public_network"

  # Share an additional folder to the guest VM. The first argument is
  # the path on the host to the actual folder. The second argument is
  # the path on the guest to mount the folder. And the optional third
  # argument is a set of non-required options.
  #
  # This binds our root project dir (the one that includes the Vagrantfile) 
  # to /home/vagrant/public_html (When we ssh into vagrant by default, we are put in /home/vagrant/ )
  config.vm.synced_folder "./", "/home/vagrant/public_html"

  # Customize the amount of memory on the VM:
  # vb.memory = "512"
  # hostname
  config.vm.hostname = "centos.dev"

  # Enable provisioning with a shell script. -- We can add sql build statements here later on
  # config.vm.provision "shell", inline: <<-SHELL
  #   apt-get update
  #   apt-get install -y apache2
  # SHELL
end
