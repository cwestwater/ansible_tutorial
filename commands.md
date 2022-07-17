## Test connectivity
```
ansible all --key-file ~/.ssh/ansible -i inventory -m ping
```

## Test connectivity with ansible.cfg in use
```
ansible all -m ping
```

## List hosts in inventory
```
ansible all --list-hosts
```

## Gather Facts

Gets LOADS of info on the OS

```
ansible all -m gather_facts
```

You can limit to a single host:

```
ansible all -m gather_facts --limit ubuntu01
```

## Running a command elevated
[ansible.builtin.apt module – Manages apt-packages](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/apt_module.html)
```
ansible all -m apt -a update_cache=true --become --ask-become-pass
```

## Install a package
```
ansible all -m apt -a name=tmux --become --ask-become-pass
```

## Update a package to latest
```
ansible all -m apt -a "name=tmux state=latest" --become --ask-become-pass
```

## Update all packages
```
ansible all -m apt -a upgrade=dist --become --ask-become-pass
```

## Run a simple Playbook
```
ansible-playbook --ask-become-pass install_apache.yml
```

## Module 8
[package - Generic OS package manager](https://docs.ansible.com/ansible/2.9/modules/package_module.html)

## Module 10 - targeting tags. What tags are available
```
ansible-playbook --list-tags 10-site.yml
```

## Run a Playbook against a tag
```
ansible-playbook --tags samba --ask-become-pass 10-site.yml
```

## Run a Playbook against multiple tag
```
ansible-playbook --tags "samba,db" --ask-become-pass 10-site.yml
```

## 
```

```

## 
```

```