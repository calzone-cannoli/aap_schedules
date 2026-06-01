# Project Title

Disable and Re-Enable AAP Schedules

## Description

This project contains a playbook to disable all active schedules in AAP 2.4 and a playbook to re-enable those schedules in AAP 2.6

The intent of this project is to disable schedules to allow for an AAP 2.4 to 2.6 upgrade and enable them once the upgrade is complete

Note that any schedules that were already disabled prior to running `disable_schedules.yml` will stay disabled after running `enable_schedules.yml`

## Getting Started

### Dependencies

* You must have [ansible-navigator](https://docs.ansible.com/projects/navigator/installation/) installed to run these playbooks
* Required collections:
  * ansible.controller

```sh
ansible-galaxy collection install ansible.controller
```

### Installing

* Once you have pulled down the playbooks, you will need to update the `controller_url` and `controller_token` vars in group_vars directory with your URL and API token, respectively

### Executing program

* The ansible-navigator.yml file specifies the AAP 2.6 execution environment. If you are running this on a lower environment you will need to call the EE during the run command:

```sh
ansible-navigator run disable_schedules.yml --eei registry.redhat.io/ansible-automation-platform-24/ee-supported-rhel9
```

* To disable all active schedules

```sh
ansible-navigator run disable_schedules.yml
```

* To re-enable all schedules disabled in the previous step

```sh
ansible-navigator run enable_schedules.yml
```

## Authors

Karyn Cassio and Cara Cannarozzi
