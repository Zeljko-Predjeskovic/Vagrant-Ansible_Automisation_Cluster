IMAGE_NAME = "debian/buster64"
MANAGER = 1
WORKERS = 3

Vagrant.configure("2") do |config|
    config.ssh.insert_key = false

    config.hostmanager.enabled = true
    config.hostmanager.manage_host = true
    config.hostmanager.manage_guest = true
    config.hostmanager.include_offline = true

    config.vm.provider "virtualbox" do |v|
        v.memory = 2048
        v.cpus = 2
    end

    config.vm.define "k8s-master" do |master|
        master.vm.box = IMAGE_NAME
        master.vm.network "private_network", ip: "192.168.50.10"
        master.vm.hostname = "k8s-master"
    end

    (1..WORKERS).each do |i|
        config.vm.define "k8s-worker-#{i}" do |node|
            node.vm.box = IMAGE_NAME
            node.vm.network "private_network", ip: "192.168.50.#{i + 10}"
            node.vm.hostname = "k8s-worker-#{i}"
        end
    end
end
