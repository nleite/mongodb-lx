Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/trusty64"
  config.vm.box_check_update = false
  config.vm.synced_folder "shared", "/shared", create: true

  config.vm.define "mongod-lx" do |server|
    server.vm.provider "virtualbox" do |vb|
	     vb.customize ["modifyvm", :id, "--cpus", "2"]
       vb.name = "mongod-lx"
       vb.memory = 2048
    end
    server.vm.hostname = "lx.mongodb.university"
    server.vm.network :private_network, ip: "192.168.60.60"
    server.vm.provision :shell, path: "provision", args: ENV['ARGS']
  end
end
