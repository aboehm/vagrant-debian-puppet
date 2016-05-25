# -*- mode: ruby -*-
# vi: set ft=ruby :

DEBIAN_RELEASE = "jessie"
if ENV['RELEASE'] != nil
	DEBIAN_RELEASE = ENV['RELEASE']
end

Vagrant.configure(2) do |config|
  config.vm.box = "debian/" + DEBIAN_RELEASE + "64"

  config.vm.provision "shell", inline: <<-SHELL
     wget https://apt.puppetlabs.com/puppetlabs-release-pc1-#{DEBIAN_RELEASE}.deb
     sudo dpkg -i puppetlabs-release-pc1-#{DEBIAN_RELEASE}.deb
     rm puppetlabs-release-pc1-#{DEBIAN_RELEASE}.deb
     sudo apt-get update
     sudo apt-get install --yes puppet-agent
   SHELL
end
