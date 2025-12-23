## about

devstack test drive

## setup

1. setup VM
spec
- disk: 40 GB
- cpu: 6 core
- memory: 12288 MB
install ubuntu
- set NOPASSWD to sudoers / sudo group

1. get devstack
```shell
git clone https://opendev.org/openstack/devstack -b stable/2025.2
wget -O ./devstack/local.conf https://opendev.org/openstack/neutron/raw/branch/master/devstack/ovn-local.conf.sample
```

2. configure devstack
```conf
HOST_IP=[VM IP]
BRANCH=stable/2025.2
#BRANCH=refs/remote/origin/stable/2025.2
RECLONE=yes
```

3. setup devstack
```shell
./stack.sh
```

in case of failure, try
```shell
./unstack.sh
./clean.sh
sudo rm -rf /opt/stack
```

```shell
This is your host IP address: 172.16.146.128
This is your host IPv6 address: ::1
Horizon is now available at http://172.16.146.128/dashboard
Keystone is serving at http://172.16.146.128/identity/
The default users are: admin and demo
The password: password
```

4. setup openrc in ~/.profile
```shell
. ~/git/code0x9/devstack-test/devstack/openrc admin
```

## ref
- OVN OpenStack Tutorial: https://docs.ovn.org/en/latest/tutorials/ovn-openstack.html
