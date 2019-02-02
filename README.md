# ansible-playground

[Ansible](https://www.ansible.com/) playground to enjoy learning ansible in a multi Operating System environment

This playground use [Virtualbox](https://www.virtualbox.org/) and [Vagrant](https://www.vagrantup.com) to provision virtual machines where to play

## My environment

I'm using Linux [Fedora 29 Workstation](https://getfedora.org/workstation) with the latest updates

## Install Requirements

Requirements to start play are:
* [git](https://git-scm.com/)
* [Visual Studio Code](https://code.visualstudio.com/)
* [VirtualBox](https://www.virtualbox.org/)
* [Vagrant](https://www.vagrantup.com)
* [Python3](https://www.python.org)
* [Ansible](https://www.ansible.com/)


### Install git

```bash
sudo dnf install git
```

### Install Visual Studio Code

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo sh -c 'echo -e "[code]\nname=Visual Studio Code\nbaseurl=https://packages.microsoft.com/yumrepos/vscode\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/vscode.repo'

dnf check-update
sudo dnf install code
```

Install vscode plugins

```bash
code --install-extension vscoss.vscode-ansible
code --install-extension streetsidesoftware.code-spell-checker
code --install-extension yzhang.markdown-all-in-one
code --install-extension bbenoist.vagrant
code --install-extension marcostazi.vs-code-vagrantfile
code --install-extension ms-python.python
```

### Install VirtualBox

I recommend the following link for this work [Virtualbox - fedora]
(https://www.if-not-true-then-false.com/2010/install-virtualbox-with-yum-on-fedora-centos-red-hat-rhel/)

```bash
sudo wget http://download.virtualbox.org/virtualbox/rpm/fedora/virtualbox.repo -O /etc/yum.repos.d/virtualbox.repo
sudo dnf install -y binutils gcc make patch libgomp glibc-headers glibc-devel kernel-headers kernel-devel dkms qt5-qtx11extras libxkbcommon
sudo dnf update
sudo dnf install VirtualBox-6.0
sudo /usr/lib/virtualbox/vboxdrv.sh setup
sudo usermod -a -G vboxusers $USER
```

### Install Vagrant

check always you are using the last version

```bash
sudo dnf install -y https://releases.hashicorp.com/vagrant/2.2.3/vagrant_2.2.3_x86_64.rpm
```

#### Vagrant plugins

Install [vagrant-hostmanager](https://github.com/devopsgroup-io/vagrant-hostmanager)
```bash
vagrant plugin install vagrant-hostmanager
```

## Start playing

First of all clone this repository from github

```bash
cd ~
mkdir -p ansible-workspace
cd ansible-workspace/
git clone https://github.com/christiangda/ansible-playground.git
cd ansible-playground/
```

The better way to "isolate the blast radius --> ;)" is using Python Virtual Environments, so, create it

```bash
python3 -m venv venv
source venv/bin/activate
pip install --upgrade pip
pip install pylint
pip install rope
pip install autopep8
pip install ansible
```

Start up Vms

```bash
vagrant up
```

Test ansible is working
```bash
ansible all -m ping
```
