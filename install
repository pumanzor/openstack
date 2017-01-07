'''On Debian 8'''

apt-get update

apt-get install sudo git

adduser stack

echo "stack ALL=(ALL) NOPASSWD: ALL" >> /etc/sudoers

su stack

git clone https://git.openstack.org/openstack-dev/devstack

cd devstack

./stack.sh

