# Setup Lab
### Setup Ansible VM
Preinstall 'ansible' host.
- Change to root user
```
sudo su
```
- Set Hostname
```
hostnamectl set-hostname hostname
```
- Set Timezone
```
timedatectl set-timezone Asia/Jakarta
```
- Set static ip address
```
vim /etc/netplan/00-installer-config.yaml
```
edit this
```
    ens160:
      dhcp4: false
      addresses: [10.23.0.x/22]
      routes:
        - to: default
          via: 10.23.0.1
      nameservers:
        addresses: [1.1.1.1,8.8.8.8]
```
save & load configuration
```
netplan apply
``` 
- Update & upgrade
```
apt update -y && apt upgrade -y
``` 
- Install Ansible
```
apt install ansible
``` 
### Setup vm-ubuntu
Preinstall 'ubuntu' host.
- Change to root user
```
sudo su
```
- Set Hostname
```
hostnamectl set-hostname hostname
```
- Set Timezone
```
timedatectl set-timezone Asia/Jakarta
```
- Set static ip address
```
vim /etc/netplan/00-installer-config.yaml
```
edit this
```
    ens160:
      dhcp4: false
      addresses: [10.23.0.x/22]
      routes:
        - to: default
          via: 10.23.0.1
      nameservers:
        addresses: [1.1.1.1,8.8.8.8]
```
save & load configuration
```
netplan apply
``` 
- Update & upgrade
```
apt update -y && apt upgrade -y
``` 
### Setup vm-centos
Preinstall 'centos' host.
- Change to root user
```
sudo su
```
- Set Hostname
```
hostnamectl set-hostname hostname
```
- Set Timezone
```
timedatectl set-timezone Asia/Jakarta
```
- Set static ip address
```
nmtui
```
- Update & upgrade
```
yum update -y && yum upgrade -y
``` 

### SSH Checking
On all managed server check ssh service
```
systemctl status sshd
ss -tunlp | grep sshd
```