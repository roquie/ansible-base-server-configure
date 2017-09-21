Ansible playbook for basic server configuring
---------------------------------------------

This Playbook is a just compilation of different roles what needed to install on "each server".  
<br>
Contains:
* [tersmitten.locales](https://github.com/Oefenweb/ansible-locales) - to prevent i18n-based errors. Like as, when PostgreSQL discard the import SQL-file if encoding does not match.
* [galexrt.ansible-ntpdate](https://github.com/galexrt/ansible-ntpdate) - to prevent errors if servers are in the cluster (one of variant of usage). However, this role and so useful.
* [dev-sec.ssh-hardening](https://github.com/dev-sec/ansible-ssh-hardening.git) - provides numerous security-related ssh configurations, providing all-round base protection
* [geerlingguy.docker](https://github.com/geerlingguy/ansible-role-docker) - Docker. Without him you can no longer live :)

## Warning

Warning: Ansible role `dev-sec.ssh-hardening` disables root-login on the target server! 
Please make sure you have another user with su or sudo permissions 
that can login into the server.

## Install

* Clone repo and jump to directory
* `ansible-galaxy install -r requirements.yml`
* `cp inventory/production-example inventory/production`
* make sure what `hosts` file in the `inventory/production` directory contains existing hosts.
* make sure for server connection via ssh key
* make sure what you read the Warning message above
* edit `playbooks/configure.yml` as your needs
* `ansible-playbook -i inventory/production playbooks/configure.yml`

## Variants of usage

* `ansible-playbook -i inventory/production playbooks/configure.yml` - will be installed all of things in requirements file.
* `ansible-playbook -i inventory/production playbooks/configure.yml --tags=base_configure` - without Docker
* `ansible-playbook -i inventory/production playbooks/configure.yml --tags=docker` - only Docker

## Todo

* `firewall`

## Pull requests

Any PR are welcome!

## Vagrant

* `vagrant up`

## License

MIT.