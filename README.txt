ansible -i inventory -m ping webservers (status)
ansible-playbook webserver_install.yml -i inventory --syntax-check (check playbook syntax)
ansible-playbook -i inventory webserver_install.yml  (run tasks)
ansible -m setup web01 (show config list)