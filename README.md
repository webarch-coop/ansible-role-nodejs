# Ansible Debian Node.js Role 

This repository contains an Ansible role for [installing Node.js on Debian and
Ubuntu servers](https://nodejs.org/en/download/package-manager/), based on the
[installation
instructions](https://github.com/nodesource/distributions/blob/master/README.md#installation-instructions),
see the [apt sources.list template](templates/nodejs.list.j2).

The role will currently install Node.js v14.x by default, see [the other
available
versions](https://github.com/nodesource/distributions/blob/master/README.md#installation-instructions).

Additional packages, to be installed globally, can be added to [the default
list](defaults/main.yml):

```yml
nodejs_packages:
  - sass
```

