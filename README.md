# Webarchitects Ansible Node.js role

[![pipeline status](https://git.coop/webarch/nodejs/badges/master/pipeline.svg)](https://git.coop/webarch/nodejs/-/commits/master)

This repository contains an Ansible role for installing [Node.js](https://nodejs.org/en/about/releases/), on Debian and Ubuntu using either [binary packages](https://github.com/nodejs/help/wiki/Installation#how-to-install-nodejs-via-binary-archive-on-linux) or [NodeSource apt packages](https://github.com/nodesource/distributions/blob/master/README.md#installation-instructions).

See the [Node.js vulnerabilities blog](https://nodejs.org/en/blog/vulnerability/) and the [GitHub node releases](https://github.com/nodejs/node/releases) for keeping up to date with the latest versions.

## Role variables

See the [defaults/main.yml](defaults/main.yml) file for the default variables, the [vars/main.yml](vars/main.yml) file for the preset variables and the [meta/argument_specs.yml](meta/argument_specs.yml) file for the variable specification.

| Variable name          | Default value  | Comment                                                                                                                                                                                                                                                                                 |
|------------------------|----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `nodejs`               | `false`         | Set to `true` for all the tasks in this role to be run.                                                                                                                                                                                                                                |
| `nodejs_download_path` | `/root/nodejs` | Path to use for downloading binary packages, GPG signatures and SHA256SUM files.                                                                                                                                                                                                        |
| `nodejs_install`       | `nodesource`   | Set to `binary` for [tar archives from GitHub](https://github.com/nodejs/node/releases) or `nodesource` for a [apt install](https://github.com/nodesource/distributions)                                                                                                                |
| `nodejs_packages`      | `[]`           | Additional node packages to install                                                                                                                                                                                                                                                     |
| `nodejs_src`           | `false`        | Set to `true` to enable the NodeSource source package repo                                                                                                                                                                                                                              |
| `nodejs_version`       | `16`           | For binary installs a [version number](https://github.com/nodejs/node/releases) like `16.15.1` or a symlink from [the archive](https://nodejs.org/dist/) like `latest-v16.x` or `latest` for the very latest release, for NodeSource `apt` based installs an integer, for example `16`  |

## Usage

This role requires [JC](https://github.com/kellyjonbrazil/jc) version `1.20.2` or later to be installed on the Ansible controller for the parsing of `gpg`  command output, it can be [installed using Ansible](https://git.coop/webarch/jc/).

This role can also be used with the [localhost repo](https://git.coop/webarch/localhost) to install `node` locally.

## Repository

The primary URL of this repo is [`https://git.coop/webarch/nodejs`](https://git.coop/webarch/nodejs) however it is also [mirrored to GitHub](https://github.com/webarch-coop/ansible-role-nodejs) and [available via Ansible Galaxy](https://galaxy.ansible.com/chriscroome/nodejs).

If you use this role please use a tagged release, see [the release notes](https://git.coop/webarch/nodejs/-/releases).

## Copyright

Copyright 2019-2023 Chris Croome, &lt;[chris@webarchitects.co.uk](mailto:chris@webarchitects.co.uk)&gt;.

This role is released under [the same terms as Ansible itself](https://github.com/ansible/ansible/blob/devel/COPYING), the [GNU GPLv3](LICENSE).
