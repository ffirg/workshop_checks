# workshop_checks

A smorgsbord of Ansible bits and pieces to help run RHPDS based workshops

## checkenvs.yml

Use this to run some simple sanity checks against the provisioned labs.

This will do things like ssh to the control nodes, check the Tower API for various settings.

In order to run, clone this repo and change a few values in extra_vars:

```bash
vi extra_vars
```

After that, just run:

```bash
ansible-playbook checkenvs.yml -e @extra_vars
```

This will create the inventory hosts file for you and run the checks.
Anything that comes back failed is a problem!
