VAGRANTFILE_API_VERSION = "2"
#
# Using Ubuntu 14.04 LTS
Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
    config.vm.box = "ubuntu/trusty64"
    config.vm.network :forwarded_port, guest: 8000, host: 8000
end
