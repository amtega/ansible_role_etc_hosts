# Ansible etc_hosts role

This is an [Ansible](http://www.ansible.com) role that manages /etc/hosts entries.

## Requirements

[dnspython 1.15.0+](http://www.dnspython.org) on the control machine.

## Role Variables

A list of all the default variables for this role is available in `defaults/main.yml`.

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

Tests are based on [molecule with vagrant virtual machines](https://molecule.readthedocs.io/en/latest/installation.html).

```shell
cd amtega.etc_hosts

molecule test --all
```

## License

Copyright (C) 2020 AMTEGA - Xunta de Galicia

This role is free software: you can redistribute it and/or modify it under the terms of:

GNU General Public License version 3, or (at your option) any later version; or the European Union Public License, either Version 1.2 or – as soon they will be approved by the European Commission ­subsequent versions of the EUPL.

This role is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the GNU General Public License for more details or European Union Public License for more details.

## Author Information

- Juan Antonio Valiño García.
