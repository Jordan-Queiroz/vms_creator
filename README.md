# VMs Creator
This is a simple project intended to create VMs for a Kubernetes cluster, only
for studying purposes.

## Prerequisites
* Install [Vagrant](https://linuxize.com/post/how-to-install-vagrant-on-ubuntu-18-04/)

* Install [vagrant-hostmanager](https://github.com/devopsgroup-io/vagrant-hostmanager)

## Running
Clone the project
```bash
git clone https://github.com/Jordan-Queiroz/vms_creator.git
```
Go to project's directory
```bash
cd vms_creator
```

Bring up the machines. Maybe you will be asked for sudo password because vagrant-hostmanager updates the host and guests /etc/hosts file
```bash
vagrant up
```

Setup your ssh to access the machine
```bash
# Check the machines' ID
vagrant global-status
# Output
id       name       provider   state   directory                           
---------------------------------------------------------------------------
5f52e10  k8smaster1 virtualbox running /home/user/somewhere/vms_creator  
9fdc32f  k8smaster2 virtualbox running /home/user/somewhere/vms_creator  
78dcd89  k8smaster3 virtualbox running /home/user/somewhere/vms_creator  
377dfee  worker1    virtualbox running /home/user/somewhere/vms_creator  
a626788  haproxy1   virtualbox running /home/user/somewhere/vms_creator

# Run ssh-config with all machines' ID
vagrant ssh-config 5f52e10 9fdc32f 78dcd89 377dfee a626788 > ~/.ssh/config
```

## Acessing VMs
Simply do
```bash
ssh vagrant@k8smaster1
ssh vagrant@k8smaster2
ssh vagrant@k8smaster3
ssh vagrant@worker1
ssh vagrant@haproxy1
```

## Suspending, destroying and starting up again
Suspending saves the machines' state, preserving the files. To suspend all machines:
```bash
vagrant suspend
```
To suspend a specific machine:
```bash
vagrant suspend <machine_id>
```
Destroying doesn't keep anyfiles. To detroy all machines:
```bash
vagrant destroy
```
To destroy a specific machine:
```bash
vagrant destroy <machine_id>
```
To bring back all suspended or destroyed machine:
```bash
vagrant up
```
To ring back a specific suspendend or destroyed machine:
```bash
vagrant up <machine_id>
```
