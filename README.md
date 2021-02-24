# workshop_checks

A smorgasbord of Ansible bits and pieces to help run RHPDS based workshops

## checkenvs.yml

Use this to run some simple sanity checks against the provisioned labs.

This will do things like ssh to the control nodes, check the Tower API for various settings.

In order to run, clone this repo and change a few values in extra_vars:

```bash
git clone https://github.com/ffirg/workshop_checks.git
cd workshop_checks
vi extra_vars
```

After that, just run:

```bash
ansible-playbook checkenvs.yml -e @extra_vars
```

This will create the inventory hosts file for you and run the checks.
Anything that comes back failed is a problem!

## fix_tower_config.yml

If you want to try to fix misconfigured tower config, then:

 - add the 'failed' hosts into the [fix_tower_hosts] group of the hosts file
 - run the playbook

```bash
ansible-playbook fix_tower_config.yml -e @extra_vars
```
