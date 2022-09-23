# cert-system
Certificate System build automation

This repo will go through the automation of Red Hat's Certificate System. This repo will currently install both Directory Server & Certificate System on the same system. 

## Quick Start

Clone this repository

Edit the vars/vars-* files with your information and passwords. Verify that the `<hosts>` are being called correctly in all yaml files. And update the inventory file with the proper inventory.

Once all edits are done run the following command: 
```sh
ansible-playbook -i inventory install_certificate_system.yaml
```

This playbook will call the following playbooks:
```
- subscription-manager.yaml
- update-install-packages.yaml
- security-checks.yaml
- certificate-system-prereqs.yaml
- install-ds.yaml
- install-cs.yaml
```

