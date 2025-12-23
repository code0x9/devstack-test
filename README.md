## about

devstack test drive

## setup

- need at least 40GB disk

1. get devstack
```shell
git clone https://opendev.org/openstack/devstack -b stable/2025.2
wget -O ./devstack/local.conf https://opendev.org/openstack/neutron/raw/branch/master/devstack/ovn-local.conf.sample
```

2. configure devstack
```conf
HOST_IP=[VM IP]
BRANCH=stable/2025.2
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

4. setup openrc in ~/.profile
```shell
. ~/git/code0x9/devstack-test/devstack/openrc admin
```

## ref
- OVN OpenStack Tutorial: https://docs.ovn.org/en/latest/tutorials/ovn-openstack.html
