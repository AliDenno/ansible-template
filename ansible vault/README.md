* Quick overview of the commands:
   ```sh
    ansible-vault create vault-pass.yml
    cat vault-pass.yml
    ansible-vault view vault-pass.yml
    ansible-vault edit vault-pass.yml
    ansible-vault decrypt vault-pass.yml
    ansible-vault encrypt vault-pass.yml
   ```
* The file "vault-pass.yml" is encrypted, but its content looks like this:
   ```sh
    Vault password:
    password: Ansible123
   ```
   - the playbook has a link to a false repository (only example)
   
* Execute the playbook and pass the password:
   ```sh
    ansible-playbook -i hosts ansible-vault.yml --ask-vault-pass
   ```
   
* if you don't want to type a password when you run the playbook, you can create a file with only the password of the vault as a content, that password will be used to decrypt the vault so that the variables there can be used:
   ```sh
    ansible-playbook -i hosts ansible-vault.yml --vault-password-file pass.yml
   ```
   where pass.yml has the password that decrypts the vault
