# -*- mode: ruby -*-
# vi: set ft=ruby :

$bootstrap = <<SCRIPT
sudo apt-get update
sudo apt-get -fuy -o Dpkg::Options::='--force-confold' install git

git clone https://github.com/sin9yt/ctf-tools.git /home/vagrant/ctf-tools/
/home/vagrant/ctf-tools/bin/manage-tools -s setup
SCRIPT

Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/xenial64"
  config.vm.hostname = "ctf-box"
  config.vm.provision "shell", privileged: false, inline: $bootstrap
  config.vbguest.installer_arguments = []
  config.vm.synced_folder "/home/sin9yt/pwn/ctf/2018", "/home/vagrant/files"
end
