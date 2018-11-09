# Ansible Debian Node.js Role 

This repository contains an Ansible role for [installing Node.js on Debian servers](https://nodejs.org/en/download/package-manager/).

To use this role you need to use Ansible Galaxy to install it into another repository by adding a `requirements.yml` file in that repo that contains:

```yml
---
- name: nodejs
  src: https://git.coop/webarch/upgrade.git
  version: master
  scm: git
```

To pull this repo in run:

```bash
ansible-galaxy install -r requirements.yml --force -p webarch/roles 
```

The other repo should also contain a `nodejs.yml` file that contains:

```yml
---
- name: Install Node.js
  become: yes

  hosts:
    - stretch_servers

  roles:
    - webarch/nodejs
```

And a `hosts.yml` file that contains lists of servers, for example:

```yml
---
all:
  children:
    stretch_servers:
      hosts:
        host3.example.org:
        host4.example.org:
        cloud.example.com:
        cloud.example.org:
        cloud.example.net:
```

Then it can be run as follows:

```bash
ansible-playbook nodejs.yml -i hosts.yml
```
