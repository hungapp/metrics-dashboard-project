Vagrant.configure("2") do |config|
  config.vm.box = "opensuse/Leap-15.2.x86_64"
  config.vm.box_version = "15.2.31.265"
  config.vm.boot_timeout = 600
  
  config.vm.network "forwarded_port", guest: 80, host: 8080
  config.vm.network "forwarded_port", guest: 9090, host: 9090
  config.vm.network "forwarded_port", guest: 8080, host: 8080
  config.vm.network "forwarded_port", guest: 9090, host: 8888
  config.vm.network "forwarded_port", guest: 3000, host: 3000
  config.vm.network "forwarded_port", guest: 3030, host: 3030
  config.vm.network "forwarded_port", guest: 6443, host: 6443
  config.vm.network "forwarded_port", guest: 9000, host: 9000
  config.vm.network "forwarded_port", guest: 10000, host: 10000

  config.vm.network "private_network", ip: "192.168.33.10"

  
  
  config.vm.provider "virtualbox" do |vb|
    vb.memory = "6144"
    vb.name = "k3s"
  end
  
  args = []
    config.vm.provision "k3s shell script", type: "shell", path: "scripts/k3s.sh", args: args
end
