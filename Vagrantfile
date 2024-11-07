Vagrant.configure("2") do |config|
    config.vm.box = "ubuntu/jammy64"
  
    # Configuración para el primer servidor Apache
    config.vm.define "apache1" do |apache1|
      apache1.vm.network "private_network", ip: "192.168.33.10"
      apache1.vm.provider "virtualbox" do |vb|
        vb.memory = "512"
        vb.cpus = 1
      end
      apache1.vm.provision "ansible_local" do |ansible|
        ansible.playbook = "setup_apache.yml"
      end
    end
  
    # Configuración para el segundo servidor Apache
    config.vm.define "apache2" do |apache2|
      apache2.vm.network "private_network", ip: "192.168.33.11"
      apache2.vm.provider "virtualbox" do |vb|
        vb.memory = "512"
        vb.cpus = 1
      end
      apache2.vm.provision "ansible_local" do |ansible|
        ansible.playbook = "setup_apache.yml"
      end
    end
  
    # Configuración para el servidor Nginx
    config.vm.define "nginx" do |nginx|
      nginx.vm.network "private_network", ip: "192.168.33.12"
      nginx.vm.provider "virtualbox" do |vb|
        vb.memory = "512"
        vb.cpus = 1
      end
      nginx.vm.provision "ansible_local" do |ansible|
        ansible.playbook = "setup_nginx.yml"
      end
    end
  end
  