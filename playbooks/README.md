* Run a playbook:
   -  suggested located to store playbooks is: /opt/ansible/
* Run a playbook:
   ```sh
    ansible-playbook -i hosts playBookName.yml
   ```
   if you don't wish to provide "become: true" in your playbook (being root), then do the following
   ```sh
    ansible-playbook -i hosts playBookName.yml -b
   ```
   a good practice is to provide groups in your hosts ex. [websevers] .. [ubuntu] and then in the hosts section of your **playbook** you specify the group name, ex. ubuntu:
   ```sh
    ansible-playbook -i hosts playBookName.yml -b
   ```
   that is also available for Ansible commands, for example if you are gathering setup information of hosts, you can be specific (where 'ubuntu' is defined as a group in the 'hosts_groups' file: 
   ```sh
    ansible ubuntu -i hosts_groups -m setup
   ```
* Check if a playbook **is going to work** and check its **syntax**:
   ```sh
    ansible-playbook -i hosts_groups copy_file.yml --check
    ansible-playbook -i hosts_groups copy_file.yml --syntax-check
   ```
   
* Use **notify-handlers** or **Conditions** when you want to check a condition before performing an action:
   -  ex. if App is installed then start it, if not then install it
   - see: install_httpd_with_handler.yml, install_apache_httpd.yml 

* Pass a **Variable** from the command line:
   ```sh
     ansible-playbook -i hosts_groups create_user_var.yml -e "user=emanuel"
   ```
* If you want to be selective when running a playbook, assing tags to the tasks in your playbook and pass the tag via commandline (only the tasks that correspond to the tag will be executed):
   ```sh
     ansible-playbook -i hosts_groups install_apache_httpd_index_tags.yml --tags "start_apache"
   ```
* Manages packages (depends on distro):
   -  https://docs.ansible.com/ansible/latest/modules/apt_module.html
   -  https://docs.ansible.com/ansible/latest/modules/yum_module.html

* Manage files and file properties:
   -  https://docs.ansible.com/ansible/latest/modules/file_module.html
