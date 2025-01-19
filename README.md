# Ansible-project-tomcat

This is a sample project to install Apache tomcat on a remote ubuntu OS via Ansible.

First you need two servers; first as Ansible controller the other one as ansible host.

Since Ansible uses Private Public keys to connect to other servers via SSH; you need to do the following.

Enter the command "ssh-keygen" on Ansible controller server

create the keys; then change directory to "~/.ssh" 

hit "ll" or "ls" command. you'll see id_rsa and id_rsa.pub files.

Enter the following command -----> cat ~/.ssh/id_rsa.pub | ssh user@hostname 'cat >> .ssh/authorized_keys'

this will copy the contents of the public key to host.

In order to test the connection, follow this ---> ssh -i ~/.ssh/id_rsa username@remote_host

If connection succeeded, then it's OK.

Then you need to Install Ansible


sudo apt update

sudo apt install software-properties-common

sudo add-apt-repository --yes --update ppa:ansible/ansible

sudo apt install ansible

--------------------------------------------------

Clone the Inventory and Playbook.yml file

Edit the inventory file with the IP Address of your host file.

In the end; Enter "ansible-playbook -i Inventory Playbook.yml"
