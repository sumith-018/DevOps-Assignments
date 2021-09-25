# Ansible Git Example

## Step 1 - Ansible installation
1. Connect to an EC2 instance, add a new user and install the required libraries
2. install ansible from https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html
3. Generate the SSH key
4. Create the inventory file hosts in etc/ansible/ and Store the public IP address in it.
5. Ping to check if the connection is successful  
`$ ansible all -m ping`


## Step 2 - Creating Ansible vault to store the Git username and token.
1. Generate a Personal Access Token (GitHub)
2. Create an ansible vault ‘secrets.yml’  
`$ ansible-vault create secrets.yml`
3. Store the gituser and gitpass (token) in it
> gituser: [Put Github Username]  
> gitpass: [Put Personal Access Token]


## Step 3 - Configuring the Ansible Git example playbook
1. Create the playbook gitexample.yml
2. Create an inventory file ‘ansible_hosts’. Also make sure that the private key (.pem) is in the same 
location/ is accessible using address.

## Step 4 - Launch the Playbook
Execute the playbook using the ‘ansible-playbook’ command :  
`$ ansible-palybook gitexample.yml -i ansible_hosts --user [USER NAME] --key-file ~/path/to/key --ask-vault-pass`

## Step 5 - Validate the Deployment
After the playbook runs successfully, open the browser and type :  
`$ curl -v http://[public ip address]:[port_number]`
