Vagrant.configure("2") do |config|
  config.vm.box = "100/ubuntu-16.10-puppet"

  #config.vm.network :private_network, type: "dhcp"

  config.vm.network :forwarded_port, guest: 3000, host: 13000, id: "rails",
    host_ip: "localhost", auto_correct: true
  config.vm.network :forwarded_port, guest: 1080, host: 11080,
    id: "action-mailer", auto_correct: true

  config.ssh.forward_agent = true

  config.vm.provider :virtualbox do |v|
    v.customize ["modifyvm", :id, "--memory", 1024]

    cpu_count = 2

    if RUBY_PLATFORM =~ /linux/
      cpu_count = `nproc`.to_i
    elsif RUBY_PLATFORM =~ /darwin/
      cpu_count = `sysctl -n hw.ncpu`.to_i
    end

    v.customize ["modifyvm", :id, "--cpus", cpu_count]
    v.customize ["modifyvm", :id, "--ioapic", "on"]

    v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
  end


  nsf_setting = RUBY_PLATFORM =~ /darwin/ || RUBY_PLATFORM =~ /linux/
  config.vm.synced_folder ".", "/vagrant", id: "vagrant-root"

  config.vm.synced_folder "../puppet", "/puppet", id: "puppet-local"

end
