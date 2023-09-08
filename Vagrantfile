
Vagrant.configure("2") do |config|

  config.vm.box = "gusztavvargadr/ubuntu-server"   # 1 - Box (imagem base) a ser usada por todas as vms

  config.vm.define "vm1" do |vm1|

  vm1.vm.network "forwarded_port", guest: 80, host: 8000 # 2  - Configuração de rede
  vm1.vm.network "private_network", ip: "192.168.56.10"
  vm1.vm.synced_folder "/var/www/html", "/var/www/html" #3 - Pasta Compartilhada


  #vm1.vm.provider "virtualbox" do |vb|  # Provedor de virtualização
    #vb.memory = "1024"  # Quantidade de memória RAM
    #b.cpus = 2  # Número de CPUs
     # end

  vm1.vm.provision "shell", inline: <<-SHELL #4 - Função: Servidor Web (instalar o Apache)
  apt-get update 
  apt-get install -y apache2
  SHELL

    end

    config.vm.define "vm2" do |vm2|

    vm2.vm.network "forwarded_port", guest: 80, host: 8888 # 2  - Configuração de rede
    vm2.vm.network "private_network", ip: "192.168.56.11"

    config.vm.provision "shell", inline: "apt update"
    config.vm.provision "shell", inline: "apt install -y mysql-server"

    end

    config.vm.define "vm3" do |vm3|

      vm3.vm.network "private_network", type: "dhcp"
      vm3.vm.network "public_network", type: "dhcp", bridge: "wlo1"
      vm3.vm.hostname = "vm3"
  


      # Configuração da interface privada (eth0)
      vm3.vm.provision "shell", inline: <<-SHELL
        export DEBIAN_FRONTEND=noninteractive
        sudo ip addr add 192.168.56.12/24 dev eth0
        sudo ip link set eth0 up
        echo 1 | sudo tee /proc/sys/net/ipv4/ip_forward
      SHELL
    end

    

end

