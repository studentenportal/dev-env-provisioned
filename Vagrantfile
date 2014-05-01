# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  # Every Vagrant virtual environment requires a box to build off of.
  config.vm.box = "studentenportal/dev-env"

  # Port forwarding
  config.vm.network :forwarded_port, guest: 8000, host: 8000

  # Synchronize the local repo with the server
  config.vm.synced_folder "../web", "/srv/www/studentenportal/", create: true
end
