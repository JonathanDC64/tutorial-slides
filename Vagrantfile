VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "chef/centos-7.0"
  config.ssh.forward_agent = true
  config.berkshelf.enabled = true
  config.omnibus.chef_version = :latest

  config.vm.provision "chef_solo" do |chef|
    chef.add_recipe "build-essential"
    chef.add_recipe "virtualenvwrapper"
  end
end
