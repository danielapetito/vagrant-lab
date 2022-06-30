BOX_IMAGE = "ubuntu/focal64"
#BOX_IMAGE = "debian/stretch64"
GATEWAY_NETWORK = "192.168.15.1"
#rede cabo
INTERFACE_NETWORK = "`ifconfig  | grep ^en | awk -F: '{print $1}'`"
#rede wifi
#INTERFACE_NETWORK = "wlp0s20f3"  #wifi

Vagrant.configure("2") do |config|
  config.vm.define "k3s_01" do | k3s_01|
    k3s_01.vm.box = BOX_IMAGE
    k3s_01.vm.hostname = "k3s-01"
    k3s_01.vm.network "public_network", ip: "192.168.15.50", bridge: INTERFACE_NETWORK
  end

  config.vm.provider "virtualbox" do |vb|
  vb.memory = "8192"
  vb.cpus = 4

  config.vm.provision "shell", inline: <<-SHELL
    sudo sed -i 's/PasswordAuthentication no/PasswordAuthentication yes/' /etc/ssh/sshd_config
    systemctl restart sshd  
    sudo apt-get update && apt-get install vim wget curl net-tools htop nmap openssh-server -y
    sudo route del default
    sudo route add default gw #{GATEWAY_NETWORK}
    SHELL

 end
end
