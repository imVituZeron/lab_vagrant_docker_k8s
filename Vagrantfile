Vagrant.configure("2") do |config|
    config.vm.provider "virtualbox" do |v|
        v.memory = 2048
        v.cpus = 2
    end
    
    (1..3).each do |i|
        config.vm.define "macs_#{i}" do |macs|
            macs.vm.box = "ubuntu/xenial64"
            macs.vm.hostname = "macs#{i}"
            macs.vm.network "public_network", bridge: "enp2s0"
            macs.vm.provision "shell", path: "script.sh"
        end
    end
end