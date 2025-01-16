# Ansible Skeleton
## Introduction
Top level organisation for server configuration and application install. 

## Pre-reqs
Install dependencies from Ansible Galaxy. At the moment it requires the ansible control host to have internet access.
```
$ ansible-galaxy collection list
$ ansible-galaxy collection install -r requirements.yml

Individually:  
$ ansible-galaxy collection install community.zabbix
$ ansible-galaxy role install Oefenweb.dnsmasq
```
## Examples
### Ansible Navigator (or ansible-playbook)
Some examples ansible-navigator use.
```
$ ansible-navigator run -m stdout playbooks/serverconfig.yml -i inventory/dev-servers --tags "sysctl"
$ ansible-navigator run -m stdout playbooks/serverconfig.yml -i inventory/dev-servers --check-syntax
```
When using a play/role with secrets:  
```
$ ansible-navigator run -m stdout playbooks/test2.yml -i inventory/dev-servers --playbook-artifact-enable false --vault-password-file=vault-pass
$ ansible-navigator run -m stdout playbooks/test2.yml -i inventory/dev-servers --playbook-artifact-enable false --vault-id @prompt
```
### Or traditional
Sometimes collections are not available in navigator. The container that navigator needs rebuilding.  
Traditional ansible-playbook can be used.
# Reference
Some notes & links to information & resources:

### Zabbix collection
The community-zabbix role requires a lot of workarounds. This needs researching further, and a role-wrapper producing.
See the following link for Zabbix details.
```
https://galaxy.ansible.com/ui/repo/published/community/zabbix/
```
