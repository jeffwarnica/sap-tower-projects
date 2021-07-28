# Repository Information

This repository contains a small collection of playbooks to be used with Ansible Tower as Projects in order to manage SAP related automation.

Its initial, and primary target, is for a Red Hat OpenTLC lab, though has been expanded to be more generally useful.

The playbooks contained herein are useful either as discrete steps for a Tower Workflow based deployment, as well as example playbooks handling
several of the steps one might model in Tower. The requirements to configure a local tower, job templates and inventory, are unspecified.


`play-step-*.yml` handles applying that particular role to the inventory. This implies Tower Job Templates must have a `limit` configured, at least for most of these.

`play-all.yml` is a functional reproduction of the demo tower workflow, and can be run against the included inventory, once customized.


## RHPDS SSH configuration

* Update ansible configuration and SSH configuration to use jump hosts:
  * Rename ansible.cfg-FOR-DEVELOPMENT to ansible.cfg
  * Rename ssh_config-FOR-DEVELOPMENT to ssh_config
* Fix inventory
  * Copy inventory/sample_rhpds (or just edit)
  * Mostly fix the guid