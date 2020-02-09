# Control Node Installation
### Installation steps:

1. Get a linux machine
2. Create a new user
   ```sh
    sudo adduser ansadmin
   ```
3. Add user to sudoers file 
   ```sh
    visudo
   ```
   - under root [or anywhere] 
   - ansadmin ALL=(ALL) NOPASSWD: ALL 
   - sudo su - ansadmin 
   
   
   
4. Generate ssh keys 
   - first you need to have openssh client and server
      ```sh
       sudo apt-get install openssh-client openssh-server
      ```
   - Generate ssh keys 
      ```sh
       ssh-keygen 
      ```
   - Enable password based login (not necessary) 
