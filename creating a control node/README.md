# Control Node Installation
### Installation steps:

1. Get a linux machine (VPS etc.)
	* Setup EC2 Instance (Example)
	   - Ec2 >> Amazon Linux 2 AMI (HVM) >> pick type, configure, storage 
	   - Add tag: Name:Ansible_Control_Node
	   - Security group: Ansible-SG
	   - Ports >> ssh:22, http:80, customTcp:8080  
	   - Get the pem
2. Setup hostname 
   ```sh
    sudo su -
    hostname ansible-control-node 
    vi /etc/hostname
    (Write the name ansible-control-node)
   ```
3. Create a new user
   ```sh
    sudo adduser ansadmin
    you can also,
    Passwd ansadmin
   ```
4. Add user to sudoers file 
   ```sh
    visudo
   ```
   - under root [or anywhere] 
      - ansadmin ALL=(ALL) NOPASSWD: ALL 
   ```sh
    sudo su - ansadmin 
   ```
5. Generate ssh keys 
   - first you need to have openssh client and server
      ```sh
       sudo apt-get install openssh-client openssh-server
      ```
   - Generate ssh keys 
      ```sh
       ssh-keygen 
      ```
   - Enable password based login (not necessary) (This shouldnt happen on a control node)
   - a key should be copied to the managed node 
      ```sh
       ssh-copy-id username@remote_host
      ```
6. Install Ansible
   - Forexample using yum 
      ```sh
       yum install python
       yum install python-pip
       pip install ansible
       ansible --version
       mkdir /etc/ansible
       cd /etc/ansible
       vi ansible.cfg
      ```
   - ansible.cfg
		* Add content from: https://github.com/ansible/ansible/blob/devel/examples/ansible.cfg
		* Google Ansible config file

