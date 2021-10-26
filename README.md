# Ansible Suricata Playbook

An Ansible playbook for deploying the Suricata intrusion detection system and
fetching Snort rules with Oinkmaster.


## Role Variables

Below you can find the variables with their default variables.
```yaml
suricata_sniffing_interface: eth0
suricata_sniffing_interface_type: 100M
suricata_rules_archive_url: http://rules.emergingthreats.net/open/suricata/emerging.rules.tar.gz
suricata_log_dir: /var/log/suricata/
suricata_log_dir_certs: /var/log/suricata/certs/
suricata_rules_dir: /etc/suricata/rules/
```

## Installation

From your Ansible's *roles* folder run:
```bash
git submodule add https://github.com/ajdelgado/ansible-suricata.git suricata
```

## Platforms
Tested on:
- Ubuntu focal

## Usage Example

1. Create a group called *nids*
2. Add a host with access to all traffic (a router or use port mirroring in your switch to the port where this host is connected)
Inventory example (/etc/ansible/inventories/inventory):
```yaml
---
all:
  children:
    nids:
      hosts:
        my_router:
```
3. Set the variables in group_vars matching your system
Group variables example file (/etc/ansible/inventories/group_vars/nids/nids_vars.yml):
```yaml
---
suricata_sniffing_interface: eno1
suricata_sniffing_interface_type: 1000M
suricata_rules_archive_url: http://rules.emergingthreats.net/open/suricata/emerging.rules.tar.gz
suricata_log_dir: /var/log/suricata/
suricata_log_dir_certs: /var/log/suricata/certs/
suricata_rules_dir: /etc/suricata/rules/
```
4. Create a playbook like:
Playbook example file (/etc/ansible/playbooks/nids.yml):
```yaml
- name: Set up Suricata in NIDS hosts
  hosts: nids
  roles:
    - role: suricata
```

## Dependencies

None!

## License

BSD

## Author Information

Author: Alireza Savand
Github: [github.com/Alir3z4][github-account]

Author: Antonio J. Delgado
Github: [github.com/ajdelgado][github-account]