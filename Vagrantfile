Vagrant.configure("2") do |config|
    config.vm.box = "ubuntu/xenial64"

    # Configuring host manager to update /etc/hosts
    config.hostmanager.enabled = true
    config.hostmanager.manage_host = true
    config.hostmanager.manage_guest = true
    config.hostmanager.ignore_private_ip = false
    config.hostmanager.include_offline = true

    config.vm.define "k8smaster1" do |m1|
        m1.vm.hostname="k8smaster1"
        m1.vm.network "private_network", ip: "10.0.0.10"
        m1.vm.provider "virtualbox" do |vb|
            vb.memory = 1024
        end
    end

    config.vm.define "k8smaster2" do |m2|
        m2.vm.hostname="k8smaster2"
        m2.vm.network "private_network", ip: "10.0.0.11"
        m2.vm.provider "virtualbox" do |vb|
            vb.memory = 1024
        end
    end

    config.vm.define "k8smaster3" do |m2|
        m2.vm.hostname="k8smaster3"
        m2.vm.network "private_network", ip: "10.0.0.12"
        m2.vm.provider "virtualbox" do |vb|
            vb.memory = 1024
        end
    end

    config.vm.define "worker1" do |m2|
        m2.vm.hostname="worker1"
        m2.vm.network "private_network", ip: "10.0.0.13"
        m2.vm.provider "virtualbox" do |vb|
            vb.memory = 1024
        end
    end

    config.vm.define "haproxy1" do |m2|
        m2.vm.hostname="haproxy1"
        m2.vm.network "private_network", ip: "10.0.0.14"
        m2.vm.provider "virtualbox" do |vb|
            vb.memory = 1024
        end
    end
end