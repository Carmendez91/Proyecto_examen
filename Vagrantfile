Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/xenial64"
  config.vm.network "private_network", ip:"192.168.50.55"
  config.vm.synced_folder ".","/proyecto_examen"

   config.vm.provision "shell", inline: <<-SHELL

    sudo apt install -y php php-mysqli 

    echo "-- Insertar datos de ejemplo en la tabla 'datos_menu'" > /home/vagrant/datos_menu.sql
    echo "INSERT INTO gestion_restaurante.menu(nombre, descripcion, precio, categoria) VALUES" >> /home/vagrant/datos_menu.sql
    echo "('Hamburguesa de Wagyu', 'Hamburguesa de wagyu autentica', 15, 'Carnes')," >> /home/vagrant/datos_menu.sql  
    echo "('Sopa minestrone', 'Sopa de la abuela', 10, 'Sopas')," >> /home/vagrant/datos_menu.sql
    echo "('Tartar de salmon', 'Tarta del mar del norte', 20, 'Pescado')," >> /home/vagrant/datos_menu.sql
    echo "('Brownie de chocolate', 'Brownie inspirado en la infancia', 8, 'Postres')," >> /home/vagrant/datos_menu.sql
    echo "('Sorbete de limon', 'Sorbete de limones del huerto', 5, 'Postres');" >> /home/vagrant/datos_menu.sql

    SHELL
end