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
    config.vm.define "centos6", autostart: false do |centos6|
        centos6.vm.box = "centos/6"
        centos6.vm.box_check_update = true
        centos6.vm.hostname = "centos6"
        centos6.vm.network "public_network", auto_config: true
        centos6.vm.provider "virtualbox" do |v|
            v.name = "centos6"
            v.memory = "512"
            v.cpus = 1
        end
       centos6.hostmanager.ip_resolver = proc do |vm, resolving_vm|
            if hostname = (vm.ssh_info && vm.ssh_info[:host])
                `vagrant ssh centos6 -c "hostname -I"`.split()[1]
            end
        end

        # Necessary for ansible
        centos6.vm.provision "shell", inline: "sudo yum install -y libselinux-python"
    end

    # Centos 7 vm
    config.vm.define "centos7", primary: true do |centos7|
        centos7.vm.box = "centos/7"
        centos7.vm.box_check_update = true
        centos7.vm.hostname = "centos7"
        centos7.vm.network "public_network", auto_config: true
        centos7.vm.provider "virtualbox" do |v|
            v.name = "centos7"
            v.memory = "512"
            v.cpus = 1
        end
        centos7.hostmanager.ip_resolver = proc do |vm, resolving_vm|
            if hostname = (vm.ssh_info && vm.ssh_info[:host])
                `vagrant ssh centos7 -c "hostname -I"`.split()[1]
            end
        end
    end

    # Ubuntu 18.04 (Bionic)
    config.vm.define "ubuntu1804", autostart: false do |ubuntu1804|
        ubuntu1804.vm.box = "ubuntu/bionic64"
        ubuntu1804.vm.box_check_update = true
        ubuntu1804.vm.hostname = "ubuntu1804"
        ubuntu1804.vm.network "public_network", auto_config: true
        ubuntu1804.vm.provider "virtualbox" do |v|
            v.name = "ubuntu1804"
            v.memory = "512"
            v.cpus = 1
        end
        ubuntu1804.hostmanager.ip_resolver = proc do |vm, resolving_vm|
            if hostname = (vm.ssh_info && vm.ssh_info[:host])
                `vagrant ssh ubuntu1804 -c "hostname -I"`.split()[1]
            end
        end

        # Necessary for ansible
        ubuntu1804.vm.provision "shell", inline: "sudo apt-get -y install python"
    end

    # Ubuntu 18.10 (Cosmic)
    config.vm.define "ubuntu1810", autostart: false do |ubuntu1810|
        ubuntu1810.vm.box = "ubuntu/cosmic64"
        ubuntu1810.vm.box_check_update = true
        ubuntu1810.vm.hostname = "ubuntu1810"
        ubuntu1810.vm.network "public_network", auto_config: true
        ubuntu1810.vm.provider "virtualbox" do |v|
            v.name = "ubuntu1810"
            v.memory = "512"
            v.cpus = 1
        end
        ubuntu1810.hostmanager.ip_resolver = proc do |vm, resolving_vm|
            if hostname = (vm.ssh_info && vm.ssh_info[:host])
                `vagrant ssh ubuntu1810 -c "hostname -I"`.split()[1]
            end
        end

        # Necessary for ansible
        ubuntu1810.vm.provision "shell", inline: "sudo apt-get -y install python"
    end

    # debian 8 (jessie)
    config.vm.define "debian8", autostart: false do |debian8|
        debian8.vm.box = "debian/jessie64"
        debian8.vm.box_check_update = true
        debian8.vm.hostname = "debian8"
        debian8.vm.network "public_network", auto_config: true
        debian8.vm.provider "virtualbox" do |v|
            v.name = "debian8"
            v.memory = "512"
            v.cpus = 1
        end
        debian8.hostmanager.ip_resolver = proc do |vm, resolving_vm|
            if hostname = (vm.ssh_info && vm.ssh_info[:host])
                `vagrant ssh debian8 -c "hostname -I"`.split()[1]
            end
        end

        # Necessary for ansible
        debian8.vm.provision "shell", inline: "sudo apt-get -y install python"
    end

    # debian 9 (stretch)
    config.vm.define "debian9", autostart: false do |debian9|
        debian9.vm.box = "debian/stretch64"
        debian9.vm.box_check_update = true
        debian9.vm.hostname = "debian9"
        debian9.vm.network "public_network", auto_config: true
        debian9.vm.provider "virtualbox" do |v|
            v.name = "debian9"
            v.memory = "512"
            v.cpus = 1
        end
        debian9.hostmanager.ip_resolver = proc do |vm, resolving_vm|
            if hostname = (vm.ssh_info && vm.ssh_info[:host])
                `vagrant ssh debian9 -c "hostname -I"`.split()[1]
            end
        end

        # Necessary for ansible
        debian9.vm.provision "shell", inline: "sudo apt-get -y install python"
    end

    # Amazon Linux 2 LTS
    config.vm.define "amzn2", autostart: false do |amzn2|
        amzn2.vm.box = "gbailey/amzn2"
        amzn2.vm.box_check_update = true
        amzn2.vm.hostname = "amzn2"
        amzn2.vm.network "public_network", auto_config: true
        amzn2.vm.provider "virtualbox" do |v|
            v.name = "amzn2"
            v.memory = "512"
            v.cpus = 1
        end
        amzn2.hostmanager.ip_resolver = proc do |vm, resolving_vm|
            if hostname = (vm.ssh_info && vm.ssh_info[:host])
                `vagrant ssh amzn2 -c "hostname -I"`.split()[1]
            end
        end
    end

end
