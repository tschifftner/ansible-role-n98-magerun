# Ansible Role: Install n98-magerun

[![Build Status](https://travis-ci.org/tschifftner/ansible-role-n98-magerun.svg)](https://travis-ci.org/tschifftner/ansible-role-n98-magerun)

Installs [n98-magerun](https://github.com/netz98/n98-magerun) / [n98-magerun2](https://github.com/netz98/n98-magerun2) on Debian/Ubuntu linux servers.

The n98 magerun cli tools provides some handy tools to work with Magento from command line.

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

## n98-magerun plugins

Plugins can be installed globally as well. Be careful who you trust!

```
n98_magerun_plugin_repositories:
  - repo: 'https://github.com/cmuench/cmuench-magerun-addons.git'
    dest: 'cmuench.magerun-addons'

  - repo: 'https://github.com/peterjaap/magerun-addons.git'
    dest: 'peterjaap.magerun-addons'

  - repo: 'https://github.com/aleron75/Webgriffe_Golive.git'
    dest: 'aleron75.Webgriffe_Golive'

  - repo: 'https://github.com/kalenjordan/magerun-addons.git'
    dest: 'kalenjordan.magerun-addons'

  - repo: 'https://github.com/AOEpeople/mpmd.git'
    dest: 'AOEpeople.mpmd'

  - repo: 'https://github.com/fruitcakestudio/magerun-modman.git'
    dest: 'fruitcakestudio.magerun-modman'

  - repo: 'https://github.com/tschifftner/magerun-addons.git'
    dest: 'tschifftner.magerun-addons'
```

## Dependencies

None.

## Installation

```
$ ansible-galaxy install tschifftner.n98-magerun
```

## Example Playbook

    - hosts: server
      roles:
        - { role: tschifftner.n98-magerun }

## Supported OS
## Supported OS
Ansible          | Debian Jessie    | Ubuntu 14.04    | Ubuntu 12.04
:--------------: | :--------------: | :-------------: | :-------------: 
2.0              | Yes              | Yes             | Yes


## License

MIT / BSD

## Author Information

 - [Tobias Schifftner](https://twitter.com/tschifftner), [ambimax® GmbH](https://www.ambimax.de)