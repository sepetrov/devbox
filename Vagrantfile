# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
    config.vm.hostname = "devbox"
    config.vm.box = "sepetrov/trusty64"
    config.vm.network "forwarded_port", guest: 80, host: 8080
    config.vm.network "forwarded_port", guest: 3306, host: 3360
    config.vm.network "private_network", type: "dhcp"
    config.vm.synced_folder ".", "/vagrant", type: "nfs"
    config.vm.provider "virtualbox" do |v|
        v.name = "devbox"
        v.cpus = 2
        v.memory = 1024
    end
    config.vm.provision :ansible do |ansible|
        #ansible.verbose = "vvvv"
        ansible.inventory_path = "ansible/development"
        ansible.groups = {
            "db_servers" => ["default"],
            "web_servers" => ["default"],
            "all_groups:children" => ["db_servers", "web_servers"]
        }
        ansible.extra_vars = {
            user: "vagrant",
            db_port: 3306,
            db_name: "devbox",
            db_user: "devbox",
            db_password: "devbox",
            web_name: "devbox",
            web_server_name: "devbox",
            web_port: 80,
            web_root: "/vagrant"
        }
        ansible.playbook = "ansible/playbook.yml"
    end
end
