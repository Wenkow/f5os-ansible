# F5OS Ansible automation example


This repo contains a basic ansible skeleton and playbooks as an example how to provision F5OS appliances.

Playbooks:  

* **info.yaml** - prints out the collected F5OS facts
* **ifaces.yaml** - creates defined VLANs (file group_vars/all/vlans), creates two LAG interfaces and assigns vlans to respective LAGs (internal VLANs LAG, external VLANs LAG)
* **tenant.yaml** - provisions BIGIP tenant and binds all vlans to it
* **backup.yaml** - backs up the F5OS and uploads it to the destination

## Before you start
* clone the repo
* add username and password to group_vars/all/vars
* add F5OS appliance IPs or FQDNs to inventory/default.ini

## Use the playbooks

I run the Ansible in the Python virtual environment (venv). So first create/activate a venv, install the Ansible and than go

```
python3 -m venv venv
. venv/bin/activate
pip install ansible
ansible-galaxy collection install f5networks.f5os
ansible-playbook desired_file.yaml
```