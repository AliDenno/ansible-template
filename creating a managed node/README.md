# Managed Node Installation

### Installation steps:

1. Setup an instance (aws-ec2, vps, etc.)
   - if you got an error "key too open" when connection, do the following: 
   ```sh
    chmod 400 Key
   ```

2. Setup hostname
   - be root
   ```sh
    sudo su -
   ```
   - change it in the hostname file
   ```sh
    vi /etc/hostname
   ```
   - also 
   ```sh
    hostname instance-managed-node
   ```
3. Create ansadmin user [use the same one accross environments]
   - create user ansadmin
   ```sh
     adduser ansadmin
     passwd ansadmin
   ```
4. Add user to sudoers file
   ```sh
      visudo
   ```
   - add ansadmin
   ```sh
      ansadmin ALL=(ALL) NOPASSWD: ALL
   ```
5. Enable password based login (Temporaly)
   ```sh
      vi /etc/ssh/sshd_config
   ```
   - set the following:
   ```sh
      PasswordAuthentication yes
   ```
   - restart the service:
   ```sh
      reload sshd.service
   ```
6. Creating the communication between the control node and managed nodes:
   - grab the managed node ip:
   ```sh
      ip addr
   ```
   then add it to the 'hosts' file of the control node (using the ansible user), usually:
   ```sh
      /opt/ansible/hosts 
   ```
   - copy the public key from the control node to the managed nodes to obtain access, on control node do the following:
   ```sh
      ssh-copy-id control-node-ip
   ```
