* Run a playbook:
   ```sh
    ansible-playbook -i hosts playBookName.yml
   ```
   if you don't wish to provide "become: true" in your playbook, then do the following
   ```sh
    ansible-playbook -i hosts playBookName.yml -b
   ```
   a good practice is to provide groups in your hosts ex. [websevers] .. [ubuntu] and then in the hosts section of your playbook you specify the group name, ex. ubuntu:
   ```sh
    ansible-playbook -i hosts playBookName.yml -b
   ```
* Manages packages (depends on distro):
   -  https://docs.ansible.com/ansible/latest/modules/apt_module.html
   -  https://docs.ansible.com/ansible/latest/modules/yum_module.html

* Manage files and file properties
   -  https://docs.ansible.com/ansible/latest/modules/file_module.html
