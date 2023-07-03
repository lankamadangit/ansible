## 🧰 Prerequisites

### Install Ansible

#### Commands
1. Login using SSH to the EC2
   - ssh -i KEYPAIR-CREATED-IN-AWS-EC2 ubuntu@PUBLIC-IP-ADDRESS
   - E.g ssh -i aws-ssh-login-keypair.pem ubuntu@52.15.182.125
   
2. Update & upgrade using following Linux commands 
   - sudo su
   - apt update -y
   apt upgrade -y

3. Install Ansible
   - apt install ansible

4. Commands
   - ansible --version
   - apt-cache policy ansible
   - vi /etc/ansible/ansible.cfg
    Add entries of the servers like below
	[webservers]
	hostname.com
   - Create EC2 machines and provide the public address in the ansible.cfg
   - ansible -m ping <inventory-group>
   - vi /etc/ansible/ansible.cfg
    host_key_checking = False
   - Let's not work on /etc/ansible/ansible.cfg as it is purely for ansible configs. Let's start working in folder /opt/ansible/
   - Create a file ansible_hosts inside /opt/ansible/ansible_hosts
   - Add all the servers like below
   - vi /opt/ansible/ansible_hosts
   	 [aws-servers]
	 52.15.182.125
   - Add variables needed for performing commands execution like below
     [aws-servers:vars]
     ansible_ssh_user=ubuntu
     ansible_ssh_private_key_file=/opt/ansible/ ansible.pem
   - ansible -m ping aws-servers -i ansible_hosts
   - 
   - Other ansible commands
   - ansible -m shell -a "apt update && apt -y install tree" aws-servers -i ansible_hosts
   - 
   - 
   - 
   - 
   - 
   - 

## 🔗 My Profile
[![linkedin](https://img.shields.io/badge/linkedin-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/madan-lanka-0368a9b)
