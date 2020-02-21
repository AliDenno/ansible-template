* Show hosts:
   ```sh
    ansible all -i hosts --list-hosts
   ```

 * Get different information about your hosts:
      ```sh
       ansible all -i hosts1 -m setup
      ```
      - Extract more information:
         ```sh
          ansible all -i hosts1 -m setup | grep nodename
          ansible all -i hosts1 -m setup | grep os_family
         ```
