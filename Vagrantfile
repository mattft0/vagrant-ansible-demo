# Définition de la première machine "admin"
Vagrant.configure("2") do |config|
  config.vm.define "admin" do |admin|
    admin.vm.box = "bento/ubuntu-22.04"
    admin.vm.network "private_network", ip: "192.168.50.10"
    admin.vm.provision "shell", inline: <<-SHELL
      apt-get update
      apt-get install -y ansible
    SHELL
  end

  # Définition de la deuxième machine "mysql"
  config.vm.define "mysql" do |mysql|
    mysql.vm.box = "bento/ubuntu-22.04"
    mysql.vm.network "private_network", ip: "192.168.50.20"
    mysql.vm.provision "shell", inline: <<-SHELL
      apt-get update
      apt-get install -y mysql-server
    SHELL
  end
end
