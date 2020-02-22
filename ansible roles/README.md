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
