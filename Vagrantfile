servers=[
  {
    :hostname => "test1",
    :ip => "192.168.101.11",
    :ram => "4096",
    :cpu => "4"
  },
  {
    :hostname => "test2",
    :ip => "192.168.101.12",
    :ram => "4096",
    :cpu => "4"
  },
  {
    :hostname => "test3",
    :ip => "192.168.101.13",
    :ram => "4096",
    :cpu => "4"
  }
]

Vagrant.configure("2") do |config|
  servers.each do |machine|
  # config.hostmanager.enabled = true
  # config.hostmanager.manage_host = true
  # config.hostmanager.manage_guest = true
  # config.hostmanager.ignore_private_ip = false
  # config.hostmanager.include_offline = true
  
  config.vm.define machine[:hostname] do |node|
    node.vm.network "private_network"
    node.vm.provider :libvirt do |domain|
      domain.memory = machine[:ram]
      domain.cpus = machine[:cpu]
    end
    
    node.vm.box = "generic/ubuntu2204"
    node.vm.hostname = machine[:hostname] 
  end
  end
end
