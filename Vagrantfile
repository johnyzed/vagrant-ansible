# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"
$script1= <<SCRIPT
apt-get install git python-yaml python-paramiko python-jinja2 python-simplejson sshpass git -y
git clone git://github.com/ansible/ansible.git
SCRIPT

$script2= <<SCRIPT
cd ./ansible/hacking
source ./env-setup
echo "127.0.0.1" > ~/ansible_hosts
SCRIPT

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "ubuntu/trusty64"
  config.vm.provision :shell, inline: $script1
  config.vm.provision :shell, inline: $script2, privileged: false

end
