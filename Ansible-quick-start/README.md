# Ansible-quick-start

# Ansible introduction

- check cpu details

$ cat /proc/cpuinfo

- check memory in GB or MB

cloud_user@sorowar0073c:~$ free -g

total        used        free      shared  buff/cache   available
              
Mem:              1           0           1           0           0           1

Swap:             0           0           0

cloud_user@sorowar0073c:~$ free -m


total        used        free      shared  buff/cache   available

Mem:           1956         262        1034           9         659        1536

Swap:             0           0 


# installation using CentOS 

[cloud_user@sorowar0071c ~]$ yum list epel-release

[cloud_user@sorowar0071c ~]$ sudo yum install ansible

[sudo] password for cloud_user: 


# look at the ansible config file

[cloud_user@sorowar0071c ~]$ vim /etc/ansible/ansible.cfg 


# go to inventory/host file

[cloud_user@sorowar0071c ~]$ sudo vim /etc/ansible/hosts 


# adding inventory (2 servers) in host file after line (## db-[99:101]-node.example.com)

scoldham2 ansible_host=scoldham2c.mylabserver.com

scoldham3 ansible_host=scoldham3c.mylabserver.com

- my servers from la

sorowar0072 ansible_host=sorowar0072c.websh.mylabserver.com

sorowar0073 ansible_host=sorowar0073c.websh.mylabserver.com



# create a userName=ansible who will use ansible

$ sudo useradd ansible


# add password for that user

$ sudo passwd ansible















