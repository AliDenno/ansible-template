* Run a playbook:
   ```sh
    ansible-playbook -i hosts playBookName.yml
   ```
   if you don't wish to provide "become: true" in your playbook, then do the following
   ```sh
    ansible-playbook -i hosts playBookName.yml -b
   ```
* Manages packages (depends on distro):
   -  https://docs.ansible.com/ansible/latest/modules/apt_module.html
   -  https://docs.ansible.com/ansible/latest/modules/yum_module.html
