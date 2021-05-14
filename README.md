# ansible-ovsdpdk

The repo provides ansible scripts to enable ovs-dpdk and start VMs on top of ovs-dpdk.

How to use:

Before running ansible scripts, make sure VT-d has been enabled on your hosts.

Download code and install required packages.
```
git clone https://github.com/liverbirdkte/ansible-ovsdpdk.git
cd ansible-ovsdpdk
pipenv install
pipenv shell
```

Copy sample YAML files and modify them with your desired dpdk and vm related variables
```
cp sample/vm.yml ./
cp sample/dpdk.yml ./
```

Create a file named hosts with the following format to contains hosts you want to deploy on:
```
[hosts]
xx.xx.xxx.xx
xxx.xx.xx.xx
```

Run scripts to set up ovs-dpdk:
```
ansible-playbook -i hosts dpdk.yml
```

Run scripts to lauch VMs using libvirt:
```
ansible-playbook -i hosts vm.yml
```



