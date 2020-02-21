* Show hosts:
   ```sh
    ansible all -i hosts --list-hosts
   ```

 * Get different information about your hosts:
      ```sh
       ansible all -i hosts1 -m setup
       or be more specific (where 'ubuntu' is defined as a group in the 'hosts_groups' file):
       ansible ubuntu -i hosts_groups -m setup
      ```
      - Extract more information:
         ```sh
          ansible all -i hosts1 -m setup | grep nodename
          ansible all -i hosts1 -m setup | grep os_family
         ```
