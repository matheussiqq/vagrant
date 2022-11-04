Vagrant.configure("2") do |config|
  config.vm.define "webserver" do |vm1|
    vm1.vm.hostname = "webserver"
    vm1.vm.box = "ubuntu/focal64"
    vm1.vm.network "public_network", ip: "192.168.0.130"
    
    vm1.vm.provider "virtualbox" do |vb|
      vb.name = "web"
      vb.gui = false
      vb.memory = "1024"
    end

    vm1.vm.provision "shell", inline: <<-SHELL
        apt install nginx -y
    SHELL
  end

  config.vm.define "bdmysql" do |vm2|
    vm2.vm.hostname = "bdmysql"
    vm2.vm.box = "ubuntu/focal64"
    vm2.vm.network "public_network", ip: "192.168.0.131"
    
    vm2.vm.provider "virtualbox" do |vb|
      vb.name = "bd"
      vb.gui = false
      vb.memory = "1024"
    end

    vm2.vm.provision "shell", inline: <<-SHELL
        apt install mysql-server -y
    SHELL
  end
  
end