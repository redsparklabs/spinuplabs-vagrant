Vagrant.configure(2) do |config|
  config.vm.box       = 'trusty64'
  config.vm.box_url   = 'https://cloud-images.ubuntu.com/vagrant/trusty/current/trusty-server-cloudimg-i386-vagrant-disk1.box'
  config.vm.host_name = 'spinuplabs-rails-dev'

  config.vm.network "forwarded_port", guest: 3000, host:3000
  
  config.vm.provider :virtualbox do |vb|
    vb.customize ["modifyvm", :id, "--memory", 2048]  
  end
  config.vm.provision :puppet,
    :manifests_path => 'puppet/manifests',
    :module_path    => 'puppet/modules',
    :manifest_file  => 'default.pp',
    :options        => '--verbose'
end
