status
```
ansible -m ping webservers
```
check playbook syntax
```
ansible-playbook webserver_installation.yml --syntax-check
```
run tasks
```
ansible-playbook webserver_installation.yml
```
show config list
```
ansible -m setup web01
```