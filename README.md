##Openstack on Debian 8

###Ultra rapid installation

:one: Instalar debian 8 sistema base y openssh server

:two: Actualizar los repositorios con

> apt-get update

:three: Crear el usuario stack

> adduser stack

:four: Instalar sudo y git

> apt-get install git sudo

:five: Conceder permisos de administrador al usuario stack

> echo "stack ALL=(ALL) NOPASSWD: ALL" >> /etc/sudoers

:six: Iniciar como usuario stack

> su stack

:seven: Download devstack

> git clone https://git.openstack.org/openstack-dev/devstack

> cd devstack

:eight: Dentro de este directorio crear un archivo con el nombre `local.conf` y poner lo siguiente dentro de el:

```
[[local|localrc]]
FLOATING_RANGE=192.168.143.224/27
FIXED_RANGE=10.12.11.0/24
FIXED_NETWORK_SIZE=256
FLAT_INTERFACE=eth0
ADMIN_PASSWORD=clave
DATABASE_PASSWORD=$ADMIN_PASSWORD
RABBIT_PASSWORD=$ADMIN_PASSWORD
SERVICE_PASSWORD=$ADMIN_PASSWORD
```

:nine: Guardar el archivo e iniciar el instalador

> ./stack.sh

:keycap_ten: Una vez que termine la instalacion (varios minutos incluso horas si el equipo no posee bastante cpu y ram asi que recomiendo ir por una :pizza: o una :beer:) iniciar desde un navegador poniendo la direccion IP donde fue instalado Debian 8

> http://IP_DEBIAN/

:cloud: El usuario es admin y la clave fue definida en el archivo local.conf (ADMIN_PASSWORD=)


