# Ansible etc_hosts role

This is an [Ansible](http://www.ansible.com) role that manages /etc/hosts entries.

## Requirements

[Ansible 2.7+](http://docs.ansible.com/ansible/latest/intro_installation.html)

## Role Variables

A list of all the default variables for this role is available in `defaults/main.yml`.

## Dependencies

- [amtega.check_platform](https://galaxy.ansible.com/amtega/check_platform)
- [amtega.select_hostvars](https://galaxy.ansible.com/amtega/select_hostvars)

## Example Playbook

This is an example playbook:

```yaml
---

- hosts: all
  roles:
    - amtega.etc_hosts
  vars:    
    etc_hosts:
      - address: 192.168.13.12
        state: present
        hostnames:
          - acme1
          - acme2
      - address: 192.168.13.13
        state: present
        hostnames:
          - acme3
          - acme4
      - hostnames:
          - www.google.com
          - www.centos.org
        state: present                    
```

## Testing

Tests are based on vagrant virtual machines. You can setup vagrant engine quickly using the playbook `files/setup.yml` available in the role [amtega.vagrant_engine](https://galaxy.ansible.com/amtega/vagrant_engine).

Once you have vagrant, you can run the tests with the following commands:

```shell
$ cd amtega.etc_hosts/tests
$ ansible-playbook main.yml
```

## License

Copyright (C) 2019 AMTEGA - Xunta de Galicia

This role is free software: you can redistribute it and/or modify it under the terms of:

GNU General Public License version 3, or (at your option) any later version; or the European Union Public License, either Version 1.2 or – as soon they will be approved by the European Commission ­subsequent versions of the EUPL.

This role is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the GNU General Public License for more details or European Union Public License for more details.

## Author Information

- Juan Antonio Valiño García.
