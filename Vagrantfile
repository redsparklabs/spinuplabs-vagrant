Vagrant.configure(2) do |config|
#Vagrant::Config.run do |config|
  config.vm.box       = 'precise64'
  config.vm.box_url   = 'http://files.vagrantup.com/precise64.box'
  config.vm.host_name = 'spinuplabs-vagrant'

  config.vm.network "forwarded_port", guest: 3000, host:3000
  
  config.vm.provider :virtualbox do |vb|
    #vb.gui = true
    # only needed if you are running vb with NAT network
    #vb.customize ["modifyvm", :id, "--natdnsproxy1", "off"]
    # set the memory for the box
    vb.customize ["modifyvm", :id, "--memory", 4096]  
  end
  config.vm.provision :puppet,
    :manifests_path => 'puppet/manifests',
    :module_path    => 'puppet/modules',
    :manifest_file  => 'default.pp'
end
