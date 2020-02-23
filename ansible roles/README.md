* Creating a role:
   ```sh
    ansible-galaxy init role-name
    
    
    cd role-name
    tree
   ```
   ![image](https://user-images.githubusercontent.com/6619191/75101234-76f12200-55d9-11ea-9a65-d35afc555a55.png)


* References:
    - [Role Directory Structure](https://docs.ansible.com/ansible/latest/user_guide/playbooks_reuse_roles.html)
    - [Using Variables](https://docs.ansible.com/ansible/latest/user_guide/playbooks_variables.html#playbooks-variables)
    - Example project structure:
       ```sh
            site.yml
            webservers.yml
            fooservers.yml
            roles/
                common/
                    tasks/
                    handlers/
                    files/
                    templates/
                    vars/
                    defaults/
                    meta/
                webservers/
                    tasks/
                    defaults/
                    meta/
       ```
