# Automating-AWS-VPC-with-Ansible
Implementing automation in AWS PVC services using Ansible playbook

<img width="1248" alt="Screenshot 2023-06-22 at 15 24 18" src="https://github.com/Mamiololo01/Automating-AWS-VPC-with-Ansible/assets/67044030/aa8498cd-53a2-4835-92a7-f8614949e6ab">


To eliminate manual process and human errors in deploying PVC services in cloud, we are going to automate the process using Ansible.  The following are some of the advantages of using Ansible:

Configuration management of VPC

Automatic set up (No human errors)

Centralize change management

Version control (IAAC)

Required tools

Ansible (configuration management of VPC)

AWS (VPC set up with bastion host)

Python boto3

Flow of execution

Login to AWS

Create ec2 instance to run ansible playbook

Install Ansible

Install boto3

Set up ec2 role for ansible

Create a project dir

Sample cloud tasks(with key pair)

Create Variables Files for VPC and Bastion host

Creat VPC Setup playbook

Create Bastion setup playbook

Site.yml playbook to call both playbook at once.

Create EC2 name; control machine ansible and under advanced tab
User data
#!/bin/bash
Sudo apt update
Sudo apt install ansible -y
Create security group for ansible
Cerate the ce2 and verify ansible is running withe ansible —version command 

Create an IAM role for ansible, admin account and attach the IAM role to the EC2 instance

Validate the account is working by using the command ‘aws sts get caller identity’
You should be able to see the userid, account and arn

Creare a directory

mkdir vpc-stack-level4

cd vpc-stack-level4

Create a xml file vim test.aws.yml

Save and exit
Test reachability by using
Ansible playbook test.aws.yml
An error will occur because boto3 has  not been created
Sudo apt install python3-boto3 -y

Confirm the key is working.. Edit he vi file again and add name, copy, content and copy the digest mash of the key

Save and exit
Execute the command again Ansible playbook test.aws.yml
Confirm key is created on AWS cloud and use ls command to confirm key inside the directory.

