Ansible Suricata Playbook
=========================

An Ansible playbook for deploying the Suricata intrusion detection system and
fetching Snort rules with Oinkmaster.


Role Variables
--------------

List of Variables available to be configure:

* `suricata_sniffing_interface`
* `suricata_sniffing_interface_type`
* `suricata_rules_archive_url`
* `suricata_log_dir`
* `suricata_log_dir_certs`
* `suricata_rules_dir`


Below you can find the variables with their default variables.
```yaml
suricata_sniffing_interface: eth0
suricata_sniffing_interface_type: 100M
suricata_rules_archive_url: http://rules.emergingthreats.net/open/suricata/emerging.rules.tar.gz
suricata_log_dir: /var/log/suricata/
#suricata_log_dir: /var/log/suricata/files/
suricata_log_dir_certs: /var/log/suricata/certs/
suricata_rules_dir: /etc/suricata/rules/
```


Dependencies
-------------
None!


License
-------

BSD

Author Information
------------------

Author: Alireza Savand  
Github: [github.com/Alir3z4][github-account]


[github-account]: https://github.com/Alir3z4
