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

6.- Iniciar como usuario stack

> su stack

7.- Download devstack

> git clone https://git.openstack.org/openstack-dev/devstack
> cd devstack

8.- Dentro de este directorio crear un archivo con el nombre 'local.conf' y poner lo siguiente dentro de el:

'''
[[local|localrc]]
FLOATING_RANGE=192.168.143.224/27
FIXED_RANGE=10.12.11.0/24
FIXED_NETWORK_SIZE=256
FLAT_INTERFACE=eth0
ADMIN_PASSWORD=clave
DATABASE_PASSWORD=$ADMIN_PASSWORD
RABBIT_PASSWORD=$ADMIN_PASSWORD
SERVICE_PASSWORD=$ADMIN_PASSWORD
'''

9.- Guardar el archivo e iniciar el instalador

> ./stack.sh

10.- Una vez que termine la instalacion (varios minutos incluso horas si el equipo no posee bastante cpu y ram) iniciar desde un navegador poniendo la direccion IP donde fue instalado Debian 8

> http://IP_DEBIAN/

11.- El usuario es admin y la clave fue definida en el archivo local.conf


