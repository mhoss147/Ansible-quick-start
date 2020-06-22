# Ansible-quick-start

https://docs.ansible.com/



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

sorowar0072 ansible_host=sorowar0072c.mylabserver.com

sorowar0073 ansible_host=sorowar0073c.mylabserver.com


# create a userName=ansible who will use ansible

$ sudo useradd ansible



- connect to server sorowar0072

[cloud_user@sorowar0071c ~]$ ssh sorowar0072c.mylabserver.com


- add user named=ansible here too; also password

[cloud_user@sorowar0072c ~]$ sudo useradd ansible

[cloud_user@sorowar0072c ~]$ sudo passwd ansible


- copy key to above server

[ansible@sorowar0071c ~]$ ssh-copy-id sorowar0072c.mylabserver.com

give ansible password for that server


- go to ...72 server

[ansible@sorowar0071c ~]$ ssh sorowar0072c.mylabserver.com


(increase the permission in ...72 server, hence)

- log out and log back to ..72 as cloud_user

[ansible@sorowar0072c ~]$ logout

[ansible@sorowar0071c ~]$ ssh cloud_user@sorowar0072c.mylabserver.com



- lets allow the power like root user without password; change after line 110 # %wheel        ALL=(ALL)       NOPASSWD: ALL


line 111:  ansible        ALL=(ALL)       NOPASSWD: ALL


(to see line number ESC :set number)

- log in as ansible user

[cloud_user@sorowar0072c ~]$ sudo su - ansible


- become root

[ansible@sorowar0072c ~]$ sudo su



- logout from server ...72


[cloud_user@sorowar0072c ~]$ logout


# log in as ansible user

[cloud_user@sorowar0071c ~]$ sudo su - ansible



# genrate ssh key

$ ssh-keygen



# ansible documentation in terminal

[cloud_user@sorowar0071c ~]$ ansible-doc -s lineinfile


# Ansible ad-hoc commands are the foundation of how to work with Ansible

- ad-hoc comands are single command to execute



- use ansible setup module

[ansible@sorowar0071c ~]$ ansible sorowar0072 -m setup | less



























