Role Name
=========

Kaka ansible role for debian family.

Requirements
------------

aws account 
create two ec2-instance one for ansible and one for worker node where your kafka will install
for ansible you can create t2.miro instance 
for kafka you have to create atleast 2core cpu and 4gb ram so you can use t2.medium instance


Commands
--------------

for ansible you have to create connection in between ansible node and worker node via ssh
Ssh-keygen is a tool for creating new authentication key pairs for SSH. Such key pairs are used for automating logins, single sign-on, and for authenticating hosts.

paste below command in ansible server 

1- ssh-keygen 
2- cat /home/ubuntu/.ssh/*.pub

copy this .pub key and paste in worker node
 
3- vi /home/ubuntu/.ssh/authorized_keys

Paste your worker node IP in inventory file or you can use default path /etc/ansible/hosts 
now check the ssh connection in between ansible node and worker node


4- ansible all -m ping 

If ping is successfull then run 

5- ansible-plybook -i inventory kafka.yml


