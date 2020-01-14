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
            # Access Internet
            vb.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
            vb.customize ["modifyvm", :id, "--natdnsproxy1", "on"]
            # Config memory
            vb.memory = 1024
        end
    end

    config.vm.define "k8smaster2" do |m2|
        m2.vm.hostname="k8smaster2"
        m2.vm.network "private_network", ip: "10.0.0.11"
        m2.vm.provider "virtualbox" do |vb|
            # Access Internet
            vb.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
            vb.customize ["modifyvm", :id, "--natdnsproxy1", "on"]
            # Config memory
            vb.memory = 1024
        end
    end
end