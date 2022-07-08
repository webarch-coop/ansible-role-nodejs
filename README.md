# Webarchitects Ansible Node.js role 

[![pipeline status](https://git.coop/webarch/nodejs/badges/master/pipeline.svg)](https://git.coop/webarch/nodejs/-/commits/master)

This repository contains an Ansible role for installing [Node.js](https://nodejs.org/en/about/releases/), on Debian and Ubuntu using either [binary packages](https://github.com/nodejs/help/wiki/Installation#how-to-install-nodejs-via-binary-archive-on-linux) or [NodeSource apt packages](https://github.com/nodesource/distributions/blob/master/README.md#installation-instructions).

See the [Node.js vulnerabilities blog](https://nodejs.org/en/blog/vulnerability/) and the [GitHub node releases](https://github.com/nodejs/node/releases) for keeping up to date with the latest versions.

The [defaults/main.yml](defaults/main.yml) variables:

| Variable name          | Default value  | Comment                                                                                                                                                                                                                                                                                 |
|------------------------|----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `nodejs`               | `true`         | Set to `false` for all the tasks in this role to be skipped.                                                                                                                                                                                                                            |
| `nodejs_download_path` | `/root/nodejs` | Path to use for downloading binary packages, GPG signatures and SHA256SUM files.                                                                                                                                                                                                        |
| `nodejs_install`       | `nodesource`   | Set to `binary` for [tar archives from GitHub](https://github.com/nodejs/node/releases) or `nodesource` for a [apt install](https://github.com/nodesource/distributions)                                                                                                                |
| `nodejs_packages`      | `[]`           | Additional node packages to install                                                                                                                                                                                                                                                     |
| `nodejs_src`           | `false`        | Set to `true` to enable the NodeSource source package repo                                                                                                                                                                                                                              |
| `nodejs_version`       | `16`           | For binary installs a [version number](https://github.com/nodejs/node/releases) like `16.15.1` or a symlink from [the archive](https://nodejs.org/dist/) like `latest-v16.x` or `latest` for the very latest release, for NodeSource `apt` based installs an integer, for example `16`  | 

This role requires [JC](https://github.com/kellyjonbrazil/jc) version `1.20.2` or later to be installed on the Ansible controller using `pip` for the parsing of GPG command output, it can be [installed using Ansible](https://git.coop/webarch/jc/), or simply run:

```bash
pip3 install jc
```

The primary URL of this repo is [`https://git.coop/webarch/nodejs`](https://git.coop/webarch/nodejs) however it is also [mirrored to GitHub](https://github.com/webarch-coop/ansible-role-nodejs) and [available via Ansible Galaxy](https://galaxy.ansible.com/chriscroome/nodejs).

If you use this role please use a tagged release, see [the release notes](https://git.coop/webarch/nodejs/-/releases).

This role can also be used with the [localhost repo](https://git.coop/webarch/localhost) to install `node` locally.
