# About

Ansible role for install [Galen automated testing Framework](http://galenframework.com/) on Debian/Ubuntu.

# Dependencies

You need to install java to use `galen` command. This is not role dependency.

# Installation

```bash
ansible-galaxy install igor_mukhin.galen
```

# Default variables

```yml
galen_packages:
  - unzip # need to unpack archive

galen_version: 1.6.2
galen_url: "https://github.com/galenframework/galen/releases/download/galen-{{ galen_version }}/galen-bin-{{ galen_version }}.zip"
galen_tmp: "/tmp/galen.zip"

galen_path: /usr/bin/galen
galen_home_path: /opt/galen
# galen_home_path: "~/.galen"

galen_owner: "{{ ansible_ssh_user }}"
galen_group: "{{ ansible_ssh_user }}"
```

# Usage

```yml
- hosts: all
  sudo: yes
  roles:
    - igor_mukhin.galen
```

# Testing

```bash
cd tests
vagrant up
```

# License

MIT
