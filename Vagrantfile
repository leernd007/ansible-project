Vagrant.configure("2") do |config|
    # ansible control machine
    config.vm.define "ansible" do |ansible|
      ansible.vm.box = "spox/ubuntu-arm"
      ansible.vm.box_version = "1.0.0"
      ansible.vm.network "private_network", ip: "192.168.56.13"
      ansible.vm.provider "vmware_desktop" do |vmware|
        vmware.gui = true
        vmware.allowlist_verified = true
      end
         config.vm.provision "shell", inline: <<-SHELL
              apt update
              apt install software-properties-common -y
              add-apt-repository --yes --update ppa:ansible/ansible -y
              apt install ansible -y
         SHELL
    end
    # web01
    config.vm.define "web01" do |web01|
      web01.vm.box = "spox/ubuntu-arm"
      web01.vm.box_version = "1.0.0"
      web01.vm.network "private_network", ip: "192.168.56.11"
      web01.vm.provider "vmware_desktop" do |vmware|
        vmware.gui = true
        vmware.allowlist_verified = true
       end
    end
    # web02
    config.vm.define "web02" do |web02|
      web02.vm.box = "spox/ubuntu-arm"
      web02.vm.box_version = "1.0.0"
      web02.vm.network "private_network", ip: "192.168.56.12"
      web02.vm.provider "vmware_desktop" do |vmware|
        vmware.gui = true
        vmware.allowlist_verified = true
       end
    end
end