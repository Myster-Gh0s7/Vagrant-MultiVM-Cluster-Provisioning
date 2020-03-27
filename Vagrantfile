BOX_IMAGE = "peruubuntu-18.04-server-amd64"
SETUP_MASTER = true
SETUP_NODES = true
NODE_COUNT = 2
MASTER_IP = "192.168.56.120"
NODE_IP_NW = "192.168.56."

Vagrant.configure("2") do |config|
  config.vm.box = BOX_IMAGE
  config.vm.box_check_update = false
  config.hostmanager.enabled = true
  config.hostmanager.manage_guest = true
  
  # config.vm.network "public_network"

  if SETUP_MASTER
    config.vm.define "master" do |mconfig|
      mconfig.vm.hostname = "master-vm"
      mconfig.vm.network :private_network, ip: MASTER_IP
      mconfig.vm.provider :virtualbox do |vb|
        vb.customize ["modifyvm", :id, "--cpus", "2"]
        vb.customize ["modifyvm", :id, "--memory", "2048"]
      end
     
    end
  end
  
   if SETUP_NODES
     (1..NODE_COUNT).each do |i|
       config.vm.define "node#{i}" do |mconfig|
        mconfig.vm.box = BOX_IMAGE
        mconfig.vm.hostname = "node#{i}.x.com"
        mconfig.vm.network "private_network", ip: NODE_IP_NW + "#{i + 10}"
        mconfig.vm.provider "virtualbox" do |v|
          v.name = "node#{i}"
          v.memory = 1024
          v.cpus = 1
        end
      end
    end
  end	
end
