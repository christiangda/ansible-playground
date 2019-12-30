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
    config.vm.define "centos7", autostart: false do |centos7|
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

    # Centos 8 vm
    config.vm.define "centos8", primary: true do |centos8|
        centos8.vm.box = "centos/8"
        centos8.vm.box_check_update = true
        centos8.vm.hostname = "centos8"
        centos8.vm.network "public_network", auto_config: true
        centos8.vm.provider "virtualbox" do |v|
            v.name = "centos8"
            v.memory = "512"
            v.cpus = 1
        end
        centos8.hostmanager.ip_resolver = proc do |vm, resolving_vm|
            if hostname = (vm.ssh_info && vm.ssh_info[:host])
                `vagrant ssh centos8 -c "hostname -I"`.split()[1]
            end
        end
    end

    # Ubuntu 14.04 (Bionic)
    config.vm.define "ubuntu1404", autostart: false do |ubuntu1404|
        ubuntu1404.vm.box = "ubuntu/trusty64"
        ubuntu1404.vm.box_check_update = true
        ubuntu1404.vm.hostname = "ubuntu1404"
        ubuntu1404.vm.network "public_network", auto_config: true
        ubuntu1404.vm.provider "virtualbox" do |v|
            v.name = "ubuntu1404"
            v.memory = "512"
            v.cpus = 1
        end
        ubuntu1404.hostmanager.ip_resolver = proc do |vm, resolving_vm|
            if hostname = (vm.ssh_info && vm.ssh_info[:host])
                `vagrant ssh ubuntu1404 -c "hostname -I"`.split()[1]
            end
        end
    end

    # Ubuntu 16.04 (Bionic)
    config.vm.define "ubuntu1604", autostart: false do |ubuntu1604|
        ubuntu1604.vm.box = "ubuntu/xenial64"
        ubuntu1604.vm.box_check_update = true
        ubuntu1604.vm.hostname = "ubuntu1604"
        ubuntu1604.vm.network "public_network", auto_config: true
        ubuntu1604.vm.provider "virtualbox" do |v|
            v.name = "ubuntu1604"
            v.memory = "512"
            v.cpus = 1
        end
        ubuntu1604.hostmanager.ip_resolver = proc do |vm, resolving_vm|
            if hostname = (vm.ssh_info && vm.ssh_info[:host])
                `vagrant ssh ubuntu1604 -c "hostname -I"`.split()[1]
            end
        end

        # Necessary for ansible
        ubuntu1604.vm.provision "shell", inline: "sudo apt-get -y install python python-apt"
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
        ubuntu1804.vm.provision "shell", inline: "sudo apt-get -y install python python-apt"
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
        ubuntu1810.vm.provision "shell", inline: "sudo apt-get -y install python python-apt"
    end

    # Ubuntu 19.04 (Disco)
    config.vm.define "ubuntu1904", autostart: false do |ubuntu1904|
        ubuntu1904.vm.box = "ubuntu/disco64"
        ubuntu1904.vm.box_check_update = true
        ubuntu1904.vm.hostname = "ubuntu1904"
        ubuntu1904.vm.network "public_network", auto_config: true
        ubuntu1904.vm.provider "virtualbox" do |v|
            v.name = "ubuntu1904"
            v.memory = "512"
            v.cpus = 1
        end
        ubuntu1904.hostmanager.ip_resolver = proc do |vm, resolving_vm|
            if hostname = (vm.ssh_info && vm.ssh_info[:host])
                `vagrant ssh ubuntu1904 -c "hostname -I"`.split()[1]
            end
        end

        # Necessary for ansible
        ubuntu1904.vm.provision "shell", inline: "sudo apt-get -y install python python-apt"
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
        debian8.vm.provision "shell", inline: "sudo apt-get -y install python python-apt"
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
        debian9.vm.provision "shell", inline: "sudo apt-get -y install python python-apt"
    end

    # debian 10 (buster)
    config.vm.define "debian10", autostart: false do |debian10|
        debian10.vm.box = "debian/buster64"
        debian10.vm.box_check_update = true
        debian10.vm.hostname = "debian10"
        debian10.vm.network "public_network", auto_config: true
        debian10.vm.provider "virtualbox" do |v|
            v.name = "debian10"
            v.memory = "512"
            v.cpus = 1
        end
        debian10.hostmanager.ip_resolver = proc do |vm, resolving_vm|
            if hostname = (vm.ssh_info && vm.ssh_info[:host])
                `vagrant ssh debian10 -c "hostname -I"`.split()[1]
            end
        end

        # Necessary for ansible
        debian10.vm.provision "shell", inline: "sudo apt-get -y install python python-apt"
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
