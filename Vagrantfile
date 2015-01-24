# -*- mode: ruby -*-
VAGRANTFILE_API_VERSION = "2"
Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "chef/centos-7.0"

  config.omnibus.chef_version = :latest

  config.vm.network :private_network, ip: "10.10.10.10"

  config.vm.provision "chef_solo" do |chef|
    chef.cookbooks_path = ["./cookbooks", "./site-cookbooks"]
    chef.json = JSON.parse(File.read("./nodes/localhost.json"));
  end

end
