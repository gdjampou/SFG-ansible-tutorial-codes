# -*- mode: ruby -*- 
# vi: set ft=ruby : 
VAGRANTFILE_API_VERSION = "2" 
Vagrant.configure(VAGRANTFILE_API_VERSION) do|config| 
    config.ssh.insert_key = false 
    config.vm.provider :virtualbox do|vb| 
        vb.customize ["modifyvm", :id, "--memory", "2048"] 
    end 
    
    #Web Server 
    config.vm.define "web1" do|web| 
        web.vm.hostname = "Workstation" 
        web.vm.box = "geerlingguy/centos7" 
        web.vm.network "private_network", ip: "192.168.56.90" 
    end 
    
    #Application Server1 
    config.vm.define "app1" do|app| 
        app.vm.hostname = "webserver" 
        app.vm.box = "geerlingguy/centos7" 
        app.vm.network "private_network", ip: "192.168.56.91" 
    end 
    
    
    #Database Server 
    config.vm.define "db" do|db| 
        db.vm.hostname = "database" 
        db.vm.box = "geerlingguy/centos7" 
        db.vm.network "private_network", ip: "192.168.56.92" 
    end 
    
    config.vm.box_check_update = false 
    #config.vbguest.auto_update = false 
end

