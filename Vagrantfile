Vagrant.configure("2") do |config|
    config.vm.box = "ubuntu/xenial64"

    config.vm.define "k8smaster1" do |m1|
        m1.vm.network "private_network", ip: "10.0.0.10"
        m1.vm.provider "virtualbox" do |vb|
            vb.name = "k8smaster1"
            # Access Internet
            vb.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
            vb.customize ["modifyvm", :id, "--natdnsproxy1", "on"]
            # Config memory
            vb.memory = 1024
        end
    end

    config.vm.define "k8smaster2" do |m2|
        m2.vm.network "private_network", ip: "10.0.0.11"
        m2.vm.provider "virtualbox" do |vb|
            vb.name = "k8smaster2"
            # Access Internet
            vb.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
            vb.customize ["modifyvm", :id, "--natdnsproxy1", "on"]
            # Config memory
            vb.memory = 1024
        end
    end
end