# jonsible.xrdp

[![Build Status](https://travis-ci.com/jonsible/xrdp.svg?branch=master)](https://travis-ci.com/jonsible/xrdp)
[![Galaxy](https://img.shields.io/badge/galaxy-jonsible.xrdp-blue.svg)](https://galaxy.ansible.com/jonsible/xrdp/)

Role to install xrdp

## Requirements

To install on EL distributions, you need the EPEL repository :
```
sudo yum install epel-release
```

To install on Arch distributions, you need to install the ansible-aur module on your ansible control node :
```
git clone https://github.com/kewlfft/ansible-aur.git ~/.ansible/plugins/modules/aur
```

**⚠ WARNING ⚠**  
Firewall configuration is not managed by this role.  
You should manage it manually in your playbook.  

## Role Variables

### Default usage

As default xrdp is installed and running.
If you want to adapt this to your needs look at the [Advanced usage](#advanced-usage) section.

### Advanced usage

For more advanced usage the following variables are available:
```yaml

```

## Dependencies

None

## Example Playbook

Install xrdp with the default settings
```yaml
- hosts: all
  roles:
     - role: jonsible.xrdp
```

## License

GPL-3.0-or-later

## Author Information

This role was created in 2020 by [Jonathan Scherrer].
