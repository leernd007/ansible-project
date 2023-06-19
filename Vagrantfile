Vagrant.configure("2") do |config|
  config.hostmanager.enabled = true
  config.hostmanager.manage_host = true
  config.vm.synced_folder "./src", "/home/vagrant/src"
  ### ansible CM ###
  config.vm.define "ansible" do |ansible|
    ansible.vm.provider "vmware_desktop" do |vmware|
        vmware.gui = true
        vmware.allowlist_verified = true
    end
    ansible.vm.box = "spox/ubuntu-arm"
    ansible.vm.network "private_network", ip: "192.168.56.11"
    ansible.vm.provision "shell", inline: <<-SHELL
        apt update
        apt install software-properties-common -y
        add-apt-repository --yes --update ppa:ansible/ansible -y
        apt install ansible -y
    SHELL
  end
 ### web01 ###
   config.vm.define "web01" do |web01|
     web01.vm.box = "jacobw/fedora35-arm64"
     web01.vm.network "private_network", ip: "192.168.10.194"
     web01.vm.provider "vmware_desktop" do |vmware|
        vmware.memory = "1024"
        vmware.gui = true
        vmware.allowlist_verified = true
     end
   end
 ### web02 ###
   config.vm.define "web02" do |web02|
     web02.vm.box = "spox/ubuntu-arm"
     web02.vm.network "private_network", ip: "192.168.10.195"
     web02.vm.provider "vmware_desktop" do |vmware|
       vmware.gui = true
       vmware.allowlist_verified = true
     end
   end
end