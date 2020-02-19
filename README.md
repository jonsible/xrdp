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

## Role Variables

### Default usage

As default xrdp is installed and running.
If you want to adapt this to your needs look at the [Advanced usage](#advanced-usage) section.

### Advanced usage

For more advanced usage the following variables are available:
```yaml
xrdp_source_path: "{{ global_source_path | default('/opt') }}"
xrdp_prefix: "{{ global_prefix | default('/usr/local') }}"
xrdp_user_install: "{{ global_user_install | default(false) }}"
xrdp_user_config: "{{_global_user_config | default(false) }}"
xrdp_skel_config: "{{ global_skel_config | default(false) }}"
xrdp_install_from_source: "{{ global_install_from_source | default(false) }}"
xrdp_force_install: "{{ global_force_install | default(false) }}"
xrdp_user_strip: "{{ global_user_strip | default([]) }}"
xrdp_user_filter: "{{ global_user_filter | default([])}}"
xrdp_version: "2.9"
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
