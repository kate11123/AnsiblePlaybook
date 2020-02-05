******
How to use 
******

# Step 1. Installing Ansible 
 
* [installation guide](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html) 

# Step 2. Connect to Linux servers 
 
* You must put your keys from each server to the directory `/.ssh`
* sudo chmod 400 name-of-your-key 

# Step 3. Preparation

* Create a directory where you will work
* Put into `host.txt` ip-adrees of all your hosts
```
[staging_servers] 

example1 ansible_host=1.1.1.1

example2 ansible_host=2.2.2.2
```
* Create directory `group_vars`
* Put into `staging_servers`
```
--- 

ansible_user : your_user

ansible_ssh_private_key_file : /home/your_user/.ssh/your_key1
/home/your_user/.ssh/your_key1
```
* In the working directory create `ansible.cfg`
```
[defaults] 

host_key_checking = false 

inventory = ./hosts.txt
```
* Create `docker-compose.yml` end `.env` for your code

# Step 4. Run Playbook

`sudo ansible-playbook playbook.yml`
