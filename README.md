# Ansible Role: Install n98-magerun

[![Build Status](https://travis-ci.org/tschifftner/ansible-role-n98-magerun.svg)](https://travis-ci.org/tschifftner/ansible-role-n98-magerun)

Installs n98-magerun/n98-magerun2 on Debian/Ubuntu linux servers.

## Requirements

PHP must be installed for n98-magerun to function!
ansible 2.0+

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

```
n98_magerun_files:
  - name: 'n98-magerun for Magento 1'
    url: 'http://files.magerun.net/n98-magerun-latest.phar'
    checksum: 'md5:a92a965aa5a66d93f6b7f5c578ac9d3a'
    install: true
    dest: '/usr/local/bin/n98-magerun'

  - name: 'n98-magerun2 for Magento 2'
    url: 'http://files.magerun.net/n98-magerun2-latest.phar'
    checksum: 'md5:a0fefb45c3b5b8f6d014a37752e5fa37'
    install: true
    dest: '/usr/local/bin/n98-magerun2'
```

Checksum is not required but highly recommended for security reasons! 

## Dependencies

None.

## Installation

```
$ ansible-galaxy install tschifftner.composer
```

## Example Playbook

    - hosts: server
      roles:
        - { role: tschifftner.composer }

## Supported OS
## Supported OS
Ansible          | Debian Jessie    | Ubuntu 14.04    | Ubuntu 12.04
:--------------: | :--------------: | :-------------: | :-------------: 
1.8              | Yes              | Yes             | Yes
1.9              | Yes              | Yes             | Yes
2.0              | Yes              | Yes             | Yes


## License

MIT / BSD

## Author Information

 - Tobias Schifftner, @tschifftner