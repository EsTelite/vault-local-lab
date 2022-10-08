Vagrant.configure("2") do |config|
  config.vm.define "localstack" do |localstack|
    localstack.vm.box = "ubuntu/focal64"
    localstack.vm.network "private_network", ip: "192.168.241.10",
    name: "VirtualBox Host-Only Ethernet Adapter #4"
    localstack.vm.hostname = "localstack"
    config.vm.provision "shell",
    inline: "curl -fsSL https://get.docker.com -o get-docker.sh && sudo sh get-docker.sh && sudo snap install task --classic"
    localstack.vm.boot_timeout = 600
  config.vm.provider "virtualbox" do |vb|
    vb.memory = 3096
    vb.cpus = "3"
    vb.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
  end
  end
end
