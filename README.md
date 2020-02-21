# ansible-template

* Change defaults by changing the ansible.cfg file.
    * Configuration settings include both values from the ansible.cfg file and environment variables. Within this category, values set in configuration files have lower precedence. Ansible uses the first ansible.cfg file it finds, ignoring all others. Ansible searches for ansible.cfg in these locations in order:

          * ANSIBLE_CONFIG (environment variable if set)
          * ansible.cfg (in the current directory)
          * ~/.ansible.cfg (in the home directory)
          * /etc/ansible/ansible.cfg

    * Environment variables have a higher precedence than entries in ansible.cfg. If you have environment variables set on your control node, they override the settings in whichever ansible.cfg file Ansible loads. The value of any given environment variable follows normal shell precedence: the last value defined overwrites previous values.
Command-line options
