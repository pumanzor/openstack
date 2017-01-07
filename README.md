###openstack on Debian 8

Ultra rapid installation

1.- Instalar debian 8 sistema base y openssh server
2.- Actualizar los repositorios con

> apt-get update

3.- Crear el usuario stack

> adduser stack

4.- Instalar sudo y git

> apt-get install git sudo

5.- Conceder permisos de administrador al usuario stack

> echo "stack ALL=(ALL) NOPASSWD: ALL" >> /etc/sudoers


