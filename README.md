status
```
ansible -i inventory -m ping webservers
```
check playbook syntax
```
ansible-playbook webserver_installation.yml -i inventory --syntax-check
```
run tasks
```
ansible-playbook -i inventory webserver_installation.yml
```
show config list
```
ansible -m setup web01
```
