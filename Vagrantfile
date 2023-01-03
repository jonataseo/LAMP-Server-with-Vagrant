Vagrant.configure("2") do |config|
  # Box usada
  config.vm.box = "hashicorp/bionic64"

  # Configurações da VM
  config.vm.provider "virtualbox" do |vb|
    vb.memory = "4098"
    vb.cpus = 2
  end

  # Port Forwarding para acesso a port 80
  config.vm.network "forwarded_port", guest: 80, host: 8000

  # Instalação do Apache, Postgresql
  config.vm.provision "shell", inline: <<-SHELL
    apt-get update
    apt-get install -y apache2 postgresql php7.2 libapache2-mod-php7.2
    a2enmod php7.2
    systemctl restart apache2
  SHELL
  
end
