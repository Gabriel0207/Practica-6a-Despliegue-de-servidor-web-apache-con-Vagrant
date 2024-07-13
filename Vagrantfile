Vagrant.configure("2") do |config|
  config.vm.boot_timeout = 600 # Aumentar el tiempo de espera a 600 segundos

  # Configuración de la primera máquina virtual
  config.vm.define "web1" do |web1|
    web1.vm.box = "ubuntu/focal64" # Cambiar la caja a ubuntu/focal64
    web1.vm.network "public_network"
    web1.vm.hostname = "web1"
    web1.vm.synced_folder "./html", "/var/www/html"
    web1.vm.provider "virtualbox" do |vb|
      vb.gui = true
      vb.memory = "1024"
    end
    web1.vm.provision "shell", inline: <<-SHELL
      apt-get update
      apt-get install -y apache2
      sudo rm -rf /var/www/html
      sudo ln -fs /vagrant/html /var/www/html
    SHELL
  end

  # Configuración de la segunda máquina virtual
  config.vm.define "web2" do |web2|
    web2.vm.box = "ubuntu/focal64" # Cambiar la caja a ubuntu/focal64
    web2.vm.network "public_network"
    web2.vm.hostname = "web2"
    web2.vm.synced_folder "./html", "/var/www/html"
    web2.vm.provider "virtualbox" do |vb|
      vb.gui = true
      vb.memory = "1024"
    end
    web2.vm.provision "shell", inline: <<-SHELL
      apt-get update
      apt-get install -y apache2
      sudo rm -rf /var/www/html
      sudo ln -fs /vagrant/html /var/www/html
    SHELL
  end
end
