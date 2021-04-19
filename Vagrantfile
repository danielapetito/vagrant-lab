BOX_IMAGE = "ubuntu/focal64"
#BOX_IMAGE = "debian/stretch64"
Vagrant.configure("2") do |config|
  config.vm.define "ansible_server" do |ansible_server|
    ansible_server.vm.box = BOX_IMAGE
    ansible_server.vm.hostname = "ansible-server"
    ansible_server.vm.network "public_network", ip: "192.168.1.210", bridge: "enp2s0"
  end
  config.vm.define "ansible_vm_01" do |ansible_vm_01|
    ansible_vm_01.vm.box = BOX_IMAGE
    ansible_vm_01.vm.hostname = "ansible-vm-01"
    ansible_vm_01.vm.network "public_network", ip: "192.168.1.211", bridge: "enp2s0"
  end
  config.vm.provider "virtualbox" do |vb|
  vb.memory = "2048"
  vb.cpus = 1
  
  
  config.vm.provision "shell", inline: <<-SHELL
    sudo sed -i 's/PasswordAuthentication no/PasswordAuthentication yes/' /etc/ssh/sshd_config
    systemctl restart sshd  
    sudo apt-get update && apt-get install vim wget curl net-tools htop nmap openssh-server -y
   
    SHELL
 end 
end