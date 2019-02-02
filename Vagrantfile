# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
    # Disbled synced folder
    config.vm.synced_folder ".", "/vagrant", disabled: true

    # Enable hostnamager plugins to use hostname in Ansible inventory
    config.hostmanager.enabled = true
    config.hostmanager.manage_host = true
    config.hostmanager.manage_guest = true
    config.hostmanager.ignore_private_ip = true
    config.hostmanager.include_offline = true

    # Centos 6 vm
    config.vm.define "centos6" do |centos6|
        centos6.vm.box = "centos/6"
        centos6.vm.box_check_update = true
        centos6.vm.hostname = "centos6"
        centos6.vm.network "public_network", auto_config: true
        centos6.vm.provider "virtualbox" do |v|
            v.name = "centos6"
            v.memory = "1024"
            v.cpus = 1
        end
       centos6.hostmanager.ip_resolver = proc do |vm, resolving_vm|
            if hostname = (centos6.vm.ssh_info && centos6.vm.ssh_info[:host])
                `vagrant ssh centos6 -c "hostname -I"`.split()[1]
            end
        end
    end

    # Centos 7 vm
    config.vm.define "centos7" do |centos7|
        centos7.vm.box = "centos/7"
        centos7.vm.box_check_update = true
        centos7.vm.hostname = "centos7"
        centos7.vm.network "public_network", auto_config: true
        centos7.vm.provider "virtualbox" do |v|
            v.name = "centos7"
            v.memory = "1024"
            v.cpus = 1
        end
        centos7.hostmanager.ip_resolver = proc do |vm, resolving_vm|
            if hostname = (centos7.vm.ssh_info && centos7.vm.ssh_info[:host])
                `vagrant ssh centos7 -c "hostname -I"`.split()[1]
            end
        end
    end

    # Ubuntu 18.04 (Bionic)
    config.vm.define "ubuntu1804" do |ubuntu1804|
        ubuntu1804.vm.box = "ubuntu/bionic64"
        ubuntu1804.vm.box_check_update = true
        ubuntu1804.vm.hostname = "ubuntu1804"
        ubuntu1804.vm.network "public_network", auto_config: true
        ubuntu1804.vm.provider "virtualbox" do |v|
            v.name = "ubuntu1804"
            v.memory = "1024"
            v.cpus = 1
        end
        ubuntu1804.hostmanager.ip_resolver = proc do |vm, resolving_vm|
            if hostname = (ubuntu1804.vm.ssh_info && ubuntu1804.vm.ssh_info[:host])
                `vagrant ssh ubuntu1804 -c "hostname -I"`.split()[1]
            end
        end
    end

end
