Vagrant.configure("2") do |config|
    config.vm.box = "spox/ubuntu-arm"
    config.vm.box_version = "1.0.0"
    config.vm.network "private_network", ip: "192.168.56.11"
    config.vm.synced_folder "./src/", "/home/vagrant"
    config.vm.provider "vmware_desktop" do |vmware|
        vmware.gui = true
        vmware.allowlist_verified = true
    end
    config.vm.provision "shell", inline: <<-SHELL
        apt update
        apt install software-properties-common -y
        add-apt-repository --yes --update ppa:ansible/ansible -y
        apt install ansible -y
        apt install python3-pip -y
        pip install boto
    SHELL
end