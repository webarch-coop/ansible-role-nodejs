# Webarchitects Ansible Debian Node.js Role 

[![pipeline status](https://git.coop/webarch/nodejs/badges/master/pipeline.svg)](https://git.coop/webarch/nodejs/-/commits/master)

This repository contains an Ansible role for installing [Node.js](https://nodejs.org/en/about/releases/) on Debian and Ubuntu using either [binary packages](https://github.com/nodejs/help/wiki/Installation#how-to-install-nodejs-via-binary-archive-on-linux) or [NodeSource apt packages](https://github.com/nodesource/distributions/blob/master/README.md#installation-instructions).

The [defaults/main.yml](defaults/main.yml) variables:

| Variable name          | Default value    | Comment                                                                                                                                                |
|------------------------|------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------|
| `nodejs`               | `true`           | Set to `false` for all the tasks in this role to be skipped.                                                                                           |
| `nodejs_download_path` | `/root/nodejs`   | Path to use for downloading binary packages, GPG signatures and SHA256SUM files.                                                                       |
| `nodejs_install`       | `binary`         | Set to `nodesource` for a [apt install](https://github.com/nodesource/distributions)                                                                   |
| `nodejs_packages`      | `[]`             | Additional node packages to install                                                                                                                    |
| `nodejs_src`           | `false`          | Set to `true` to enable the NodeSource source package repo                                                                                             |
| `nodejs_version`       | `16.15.1`        | For binary installs a [version number](https://github.com/nodejs/node/releases) or `latest`, for NodeSource `apt` installs a integer, for example `16` | 

The primary URL of this repo is [`https://git.coop/webarch/nodejs`](https://git.coop/webarch/nodejs) however it is also [mirrored to GitHub](https://github.com/webarch-coop/ansible-role-nodejs) and [available via Ansible Galaxy](https://galaxy.ansible.com/chriscroome/nodejs).

If you use this role please use a tagged release, see [the release notes](https://git.coop/webarch/nodejs/-/releases).

This role can also be used with the [localhost repo](https://git.coop/webarch/localhost) to install `nodejs` locally.
