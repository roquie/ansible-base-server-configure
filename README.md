Ansible playbook for basic server configuring
---------------------------------------------

This Playbook is a just compilation of different roles what needed to install on "each server".  

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

## Todo

* `firewall`

## Pull requests

Any PR are welcome!

## Vagrant

* `vagrant up`

## License

MIT.