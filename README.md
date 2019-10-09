# Ansible Debian Node.js Role 

This repository contains an Ansible role for [installing Node.js on Debian and Ubuntu servers](https://nodejs.org/en/download/package-manager/), based on the [installation instructions](https://github.com/nodesource/distributions/blob/master/README.md#installation-instructions).

The role will currently install Node.js v11.x by default, as it is the [current LTS version](https://nodejs.org/en/about/releases/).

To use this role you need to use Ansible Galaxy to install it into another repository under `galaxy/roles/nodejs` by adding a `requirements.yml` file in that repo that contains:

```yml
---
- name: nodejs
  src: https://git.coop/webarch/nodejs.git
  version: master
  scm: git
```

And a `ansible.cfg` that contains:

```
[defaults]
retry_files_enabled = False
pipelining = True
inventory = hosts.yml
roles_path = galaxy/roles

```

And a `.gitignore` containing:

```
roles/galaxy
```

To pull this repo in run:

```bash
ansible-galaxy install -r requirements.yml --force
```

The other repo should also contain a `nodejs.yml` file that contains:

```yml
---
- name: Install Node.js
  become: yes

  hosts:
    - stretch_servers

  vars:
    nodejs_version: 11

  roles:
    - nodejs
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
ansible-playbook nodejs.yml 
```
