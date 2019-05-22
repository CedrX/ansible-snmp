SNMP Ansible role
=========

An Ansible role to configure exim4 as a relay smtp server on linux servers

Currently supports:

 * Debian
 * Ubuntu
 * RedHat

Requirements
------------

NC

Role Variables
--------------
  * *snmp_user*: authOnlyUser //for snmpv3 protocol
  * *snmp_password*: password //associated with previous variable
  * *snmp_encryption*: snmp_encryption
  * *snmp_location*: 'my society'
  * *snmp_default_community*: 'CommunityName' //for snmpv1 and snmpv2

These are OS specific and likely wont want to be changed

Debian:

  * *snmp_service_name:* snmpd
  * *snmp_configuration_file_path*: /etc/snmp/snmpd.conf
  * *snmp_package_name*: 'snmpd'

RedHat:

  * *snmp_service_name:* snmpd
  * *snmp_configuration_file_path*: /etc/snmp/snmpd.conf
  * *snmp_package_name*: 'net-snmp'

Dependencies
------------

N/A

Example Playbook
----------------

```yaml
- hosts: servers
  roles:
     - { role: snmp, tags: "mail" }
```
Call Playbook
----------------
  * ansible-playbook -i inventory_file playbook.yml

Author Information
------------------

Cedric TINTANET (Senior IT Architect)
