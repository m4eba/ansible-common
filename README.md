## Ansible Collection - m4eba.common

Install:

```
ansible-galaxy collection install m4eba.common
```

Or add to requirements.yml

```
---
collections:
  - name: m4eba.common
```

### Roles

#### disable_swap

Disable swap with swapon and /etc/fstab to be persitent after reboot.

```
tasks:
  - ansible.builtin.import_role:
      name: m4eba.common.disable_swap
```

#### update_package_cache

Works with Ubuntu, CentOS, Amazon

```
tasks:
  - ansible.builtin.import_role:
      name: m4eba.common.update_package_cache
```

#### ip_forward

Set net.ipv4.ip_forward

```
tasks:
  - ansible.builtin.import_role:
      name: m4eba.common.ip_forward
```

#### ip_nonlocal_bind

Set net.ipv4.ip_nonlocal_bind

```
tasks:
  - ansible.builtin.import_role:
      name: m4eba.common.ip_nonlocal_bind
```

#### ip_add_nat

Add SNAT rule to iptables

```
vars:
  ip_nat_source: 10.0.0.0/24    # -s source ip
  ip_nat_interface: eth0        # -o interface
  ip_nat_to_source: 23.23.9.0   # --to-source new source ip
tasks:
  - ansible.builtin.import_role:
      name: m4eba.common.ip_add_nat
```

#### ip_add_route

Add new route

```
vars:
  ip_route_address: 10.0.2.0/24 # address
  ip_route_gateway: 10.0.0.1    # gateway
tasks:
  - ansible.builtin.import_role:
      name: m4eba.common.ip_add_route
```
