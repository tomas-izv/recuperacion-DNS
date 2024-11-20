# Vagrantfile for DNSA and DNSB setup

Vagrant.configure("2") do |config|
  # Configuración de DNSA (servidor maestro)
  config.vm.define "dnsa" do |dnsa|
    dnsa.vm.box = "debian/bookworm64"
    dnsa.vm.network "private_network", ip: "192.168.57.10"
    dnsa.vm.hostname = "dnsa"
    dnsa.vm.provision "shell", inline: <<-SHELL
    sudo apt-get update
    sudo apt-get install -y bind9
    SHELL
  end

  # Configuración de DNSB (servidor esclavo)
  config.vm.define "dnsb" do |dnsb|
    dnsb.vm.box = "debian/bookworm64"
    dnsb.vm.network "private_network", ip: "192.168.57.20"
    dnsb.vm.hostname = "dnsb"
    dnsb.vm.provision "shell", inline: <<-SHELL
    sudo apt-get update
    sudo apt-get install -y bind9
    SHELL
  end
end

