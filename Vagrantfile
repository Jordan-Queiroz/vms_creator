Vagrant.configure("2") do |config|
    config.vm.box = "ubuntu/xenial64"

    config.vm.define "k8smaster1"

    config.vm.provider "virtualbox" do |v|
        # Access Internet
        v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
        v.customize ["modifyvm", :id, "--natdnsproxy1", "on"]
        # Config memory
        v.memory = 1024
    end

    # # Public to all machines see each other
    # config.vm.network "public_network", ip: "192.168.0.17"

    # # Auth stuffs
    # config.ssh.username = "root"
    # config.ssh.password = "root123"
    # config.ssh.insert_key = false

end