Vagrant.require_version ">=2.2.15"

Vagrant.configure("2") do | config |
    config.vagrant.host = :detect
    config.vm.box = "jmm288/xubuntu"
    config.vm.box_version = 1.1
    config.vm.boot_timeout = 300
    config.vm.box_check_update = true
    
    config.ssh.username = "vagrant"
    config.ssh.password = "vagrant"

    config.vm.provider "virtualbox" do |v|
        v.customize ["modifyvm", :id, "--hwvirtex", "on"]
        v.customize ["modifyvm", :id, "--nestedpaging", "on"]
        v.customize ["modifyvm", :id, "--vtxvpid", "on"]
        v.customize ["modifyvm", :id, "--largepages", "on"]
        v.customize ["modifyvm", :id, "--acpi", "on"]
        v.customize ["modifyvm", :id, "--groups", "/DevOps Development"]
        v.customize ["modifyvm", :id, "--nictype1", "virtio"]
        v.customize ["modifyvm", :id, "--nictype2", "virtio"]
        v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
        v.customize ["modifyvm", :id, "--natdnsproxy1", "on"]
        v.customize ["modifyvm", :id, "--vram", "48"]
    end

    config.vm.define "xubuntu", primary: true do |xubuntu|
        xubuntu.vm.provider "virtualbox" do |v|
            v.gui = true
            v.name = "jmm288.xubuntu"
            v.memory = 3072
            v.cpus = 2
        end
    end
end
